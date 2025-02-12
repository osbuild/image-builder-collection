# image_builder_cli

Build OS images using image-builder-cli from osbuild collection of tools.

This tool is under active development.

## Installation

    ansible-galaxy collection install git+https://github.com/osbuild/image-builder-collection,main

## Example

Create the following file:

```yaml
---
- name: Build an image
  hosts: all
  become: true
  vars:
    image_builder_cli_git_remote_repo: https://github.com/osbuild/image-builder-collection
    image_builder_cli_blueprint_filename: example-packages

    image_builder_cli_distro: fedora-40
    image_builder_cli_output_type: minimal-raw

    image_builder_cli_fetch_directory: /var/tmp/images
    image_builder_cli_fetch_image: true
    image_builder_cli_remote_delete: true
  roles:
    - osbuild.image_builder.image_builder_cli
```

Execute:

    ansible-playbook -i hostname, playbook.yml

And wait, until Ansible completes the build and fetches the image into `/var/tmp/images` on the host Ansible was called from.
