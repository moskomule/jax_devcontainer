# jax_devcontainer

devcontainer for JAX

## Requirements

`jax_devcontainer` supports `CUDA>=11.5`. Update drivers accordingly (by e.g., `udo apt-get -y install cuda-drivers`).

## VSCode

* Install the remote extentions
* Create a repository by using this repository as a template
* Clone the new repository
* Open the cloned directory using VSCode and select `reopen in container`

## Important Information

* When `tensorflow-datasets` is used, set `tf.config.experimental.set_visible_devices([], "GPU")` to avoid TF's preallocation.
* `XLA_PYTHON_CLIENT_PREALLOCATE` is set to false to avoid preallocation in the docker file. If you prefer it, comment out the line.