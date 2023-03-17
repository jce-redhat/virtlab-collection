# virt\_install\_nocloud - create a KVM virtual machine using virt-install

This role creates a virtual machine using the virt-install command, and populates a cloud-init NoCloud datasource for configuring the virtual machine after creation.  The primary use case is for creating RHEL virtual machines in a lab or demo environment.  The role assumes that an existing QCOW2 disk image with cloud-init pre-installed is used for the virtual machine's backing disk file.  Use of cloud-init can be disabled for the role if it is not present in the disk image.

The data for the NoCloud datasource is packaged as an ISO image which is attached to the virtual machine, so the `genisoimage` command must be available on the host.

To each virtual machine to be created should be in the target `hosts:` section of the playbook calling this role.  The role should be included as a task, and delegated to the host where the virtual machines will be created.

