# Terraform Enterprise Supporting Container Images

* Hashicorp provides supporting container images for Packer and Terraform.
  * packer
  * tfc-agent
  * tfci
* We need additional dependencies in the containers
  * Ansible
  * Ansible collections
  * ca-certificates
  * Packer plugins

This repo has Containerfiles that extend Hashicorm container images with our
dependencies.
