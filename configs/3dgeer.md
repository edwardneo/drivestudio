# 3DGEER: 3D Gaussian Rendering Made Exact and Efficient for Generic Cameras

> This is an unofficial implementation of 3DGEER

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
    As 3DGEER does not support camera pose training as of June 2026, you may have to comment out `CamPose` under `model`. An example OmniRe + 3DGEER config can be found [here](./omnire_geer.yaml).

3. Train the model according to the [README](../README.md#training)!