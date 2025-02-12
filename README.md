# Ansible Collection - osbuild.image_builder

Image Builder (osbuild) is a tool and service for building and composing operating system images. It is
designed to be a modern alternative to the traditional tools like kickstart, pungi, and lorax. It is based on the
concept of pipelines, where each pipeline is a sequence of stages that transform the input data into the final image.
The pipelines are defined in a JSON format and can be easily shared and reused. The service provides a REST API for
managing the pipelines and building the images. The tool is a command-line client for the service.

## osbuild.image_builder.image_builder_cli

See [osbuild.image_builder.image_builder_cli](roles/image_builder_cli)
