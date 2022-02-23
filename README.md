# jax_devcontainer

devcontainer for JAX

## Requirements

`jax_devcontainer` supports `CUDA>=11.5`. Update drivers accordingly (by e.g., `sudo apt-get -y install cuda-drivers`).

## VSCode

* Install the [remote extentions](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)
* Create a repository by using this repository as a template
* Clone the new repository
* Open the cloned directory using VSCode and select `reopen in container`

## Important Information

* Inside the docker container, you are a root user. Be careful.
* A generated docker image is large (around 10GB).
* When `tensorflow-datasets` is used, set `tf.config.experimental.set_visible_devices([], "GPU")` to avoid TF's preallocation.
* `XLA_PYTHON_CLIENT_PREALLOCATE` is set to false to avoid preallocation in the docker file. If you prefer it, comment out the line.