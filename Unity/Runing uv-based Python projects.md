This page is a guide on how to set up and run [uv-based](https://docs.astral.sh/uv/) Python projects on the Unity cluster. We will use the [LSTM Sensitivity](https://github.com/Hydro-Umass/lstm-sensitivity) project as the example.

Start by logging into Unity and then cloning/copying the code

```bash
git clone https://github.com/Hydro-Umass/lstm-sensitivity
```

the enter the directory
```bash
cd lstm-sensitivity
```

and load the necessary modules
```bash
module load cuda/12.8 cudnn/8.9.7.29-12-cuda12.8 py-uv/0.4.27
```

The CUDA modules are only necessary if you will be using a GPU (e.g., training a deep learning model).

After the modules are loaded, we can use `uv` to install all our project dependencies
```bash
uv sync
```

The installation time on the number of packages that need to be installed, but should be much faster than `conda`.

If you are planning to use Jupyter, you can run
```bash
uv run jupyter lab
```
and then connect through the web-based portal (OnDemand) to a Jupyter Lab instance. You should see the option of a notebook with the kernel that has the same name as your project.

Start the notebook and you should have all the packages described in your `pyproject.toml` specification.