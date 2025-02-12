# image_builder_cli

Build OS images using image-builder-cli from osbuild collection of tools.

This tool is under active development.

## Installation

    ansible-galaxy collection install git+https://github.com/osbuild/image-builder-collection,main

## Example

Create a blueprint and commit it into a git repository reachable by the build host:

```
vi base-image.toml
git commit -m "Update base-image" base-image.toml
git push
```

For testing purposes, there are few example blueprints in this git repository, branch named `main`, the one it is used in the next section is named `example-packages.toml`.

Create the following playbook:

```yaml
---
- name: Build an image
  hosts: all
  become: true
  vars:
    # change to the git URL, branch and file name
    image_builder_cli_git_remote_repo: https://github.com/osbuild/image-builder-collection
    image_builder_cli_blueprint_filename: example-packages

    # see image-builder-cli documentation for more info
    image_builder_cli_distro: fedora-40
    image_builder_cli_output_type: minimal-raw

    # image destination
    image_builder_cli_fetch_directory: /var/tmp/images
    image_builder_cli_fetch_image: true
    image_builder_cli_remote_delete: true
  roles:
    - osbuild.image_builder.image_builder_cli
```

Execute:

    ansible-playbook -i hostname, playbook.yml

And wait, until Ansible completes the build and fetches the image into `/var/tmp/images` on the host Ansible was called from.

## Variables

See [defaults](roles/image_builder_cli/defaults/main.yml) variables.

## Distributions and image types

See [image-builder-cli](https://github.com/osbuild/image-builder-cli) documentation for more info.
