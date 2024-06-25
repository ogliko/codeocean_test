# hash:sha256:92aa8c22119377bbd8b50e5743f64abcdd4b9d90dd00878f9f42b43873b0194f
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/jupyterlab:3.6.1-miniconda4.12.0-python3.9-ubuntu20.04

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN conda install -y --channel=defaults \
        scipy==1.9.1 \
        seaborn==0.12.2 \
    && conda clean -ya

RUN pip install -U --no-cache-dir \
    anndata==0.8.0 \
    colorcet==3.0.1 \
    geojson==3.0.1 \
    geopandas==0.13.1 \
    hdbscan==0.8.33 \
    nibabel==5.1.0 \
    scanpy==1.9.3 \
    scikit-learn==1.2.2 \
    shapely==2.0.1 \
    zarr==2.17.0 \
    -e git+https://github.com/AllenNeuralDynamics/thalamus-merfish-analysis@501eec8874aaa57fb59449b70c074d235e486afa#egg=thalamus-merfish-analysis
