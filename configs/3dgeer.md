# 3DGEER: 3D Gaussian Rendering Made Exact and Efficient for Generic Cameras

To use 3DGEER with any method,

1. Install the `gsplat-geer` package.
    ```bash
    git clone https://github.com/boschresearch/3dgeer/tree/gsplat-geer ./third_party/3dgeer
    cd ./third_party/3dgeer

    pip uninstall gsplat
    pip install -e . --no-build-isolation
    ```
2. In the method's config `.yaml` file, under `trainer` > `render`, add
    ```yaml
    render_mode: geer # one of default | ut | geer
    ```
    In addition, remove the `CamPose` section under `model`.
    
    > An example OmniRe + 3DGEER config can be found [here](./omnire_geer.yaml).

3. Train the model according to the [README](../README.md#training)!