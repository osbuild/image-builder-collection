# Ansible Collection - osbuild.image_builder

Image Builder (osbuild) is a tool and service for building and composing operating system images. It is
designed to be a modern alternative to the traditional tools like kickstart, pungi, and lorax. It is based on the
concept of pipelines, where each pipeline is a sequence of stages that transform the input data into the final image.
The pipelines are defined in a JSON format and can be easily shared and reused. The service provides a REST API for
managing the pipelines and building the images. The tool is a command-line client for the service.

## osbuild.image_builder.image_builder_cli

See [osbuild.image_builder.image_builder_cli](roles/image_builder_cli)

## osbuild.image_builder.image_builder_crc

See [osbuild.image_builder.image_builder_crc](roles/image_builder_crc)

## Contributors

Much of the code was adopted from the following roles or collections, thank you very much:

* https://github.com/brianaddicks/rh_console_imagebuilder 
* https://github.com/myllynen/rhel-image
* https://github.com/theforeman/foreman-operations-collection

See Ansible metadata for full list of authors.

## TODO

* Service account support
* Use side git repo with JSON blueprint
* Make use of the common blueprint (YAML) and Makefile in git to convert into YAML/JSON
