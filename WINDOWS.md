# Quick notes on setting up a windows box for development (may not be copy:paste)

 

# package management (think "apt-get" for windows)
install chocolatey 

install packages: choco install git golang python notepadplusplus 7zip 


# dev environments

visual studio code



# hyper-V w/ Powershell

start->run "optionalfeatures.exe", do a full install of mgmt tools and platform


# powershell

basic idea: install hyper-v, create a new vswitch, create a linux vm from ISO, start-vm, update, configure ssh, install packages

 

Get-NetAdapter
 
New-VMSwitch -name ExternalSwitch  -NetAdapterName Ethernet -AllowManagementOS $true

New-VMSwitch -name InternalSwitch -SwitchType Internal || New-VMSwitch -name PrivateSwitch -SwitchType Private  # create internal or private



Creating a new VM (need to work into a nice one liner)

$VMName = 'anaconda'

$VHDName = '{0}.vhdx' -f $VMName

$VMStoragePath = 'h:\virtual\vms'

$VHDStoragePath = Join-Path -Path '\\svstore\vms\Virtual Hard Disks' -ChildPath $VHDName

$UbuntuISOPath = 'h:\virtual\isos\ubuntu-16.04-server-amd64.iso'


New-VM -Name $VMName -MemoryStartupBytes 512MB -SwitchName ExternalSwitch -BootDevice CD -Path $VMStoragePath -Generation 1 -NoVHD

Set-VMMemory -VMName $VMName -DynamicMemoryEnabled $true -MinimumBytes 256MB -MaximumBytes 1GB

Set-VMProcessor -VMName $VMName -Count 2

New-VHD -Path $VHDStoragePath -SizeBytes 40GB -Dynamic -BlockSizeBytes 1MB

Add-VMHardDiskDrive -VMName $VMName -ControllerType IDE -ControllerNumber 0 -ControllerLocation 0 -Path $VHDStoragePath

Set-VMDvdDrive -VMName $VMName -ControllerNumber 1 -ControllerLocation 0 -Path $UbuntuISOPath

Start-VM