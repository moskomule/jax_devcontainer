# jax_devcontainer

devcontainer for JAX

## Dockerfile

`Dockerfile` supports `CUDA>=11.5. Update drivers accordingly (by e.g., `udo apt-get -y install cuda-drivers`).

## VSCode

* Install the remote extentions
* Clone this repository in your remote machine
* Open the cloned directory using VSCode and follow the instruction
* Run `python -c "import jax;print(jax.numpy.ones(1))"` to confirm if JAX is installed as 

## Important Information

When `tensorflow-datasets` is used, set `tf.config.experimental.set_visible_devices([], "GPU")` to avoid TF's preallocation.