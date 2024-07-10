# Mouse Hippocampal Sharp Wave Ripple Dataset Curated From Public Neuropixels Datasets (Under Construction)

![](Images/Workflow_with_scripts1.png)

## Description
A repo showcasing how to process and analyze Neuropixels LFP from the two largest publicly available datasets: the ABI Visual Behaviour and the IBL dataset.

### conda_env_ymls

Contains the .yaml files for recreating the environments used to run the allensdk and associated codes, as well as the .yaml for the ONE_ibl_env conda environment to run the IBL associated code.

### DetectingSWRs

Contains the pipelines for running the detection scripts. Each pipeline contains a config file which sets input and output as well as parameters of the pipeline, such as ripple envelope threshold, and whether to include or exclude gamma band events when computing the global level events. If one wishes to rerun the detection pipelines, these config files can be modified accordingly.

#### Example Usage
1. Start a `tmux` session (as the code can take a while to run):
    ```bash
    tmux
    ```

2. Activate the `allensdk_env` conda environment:
    ```bash
    conda activate allensdk_env
    ```

3. Change directory to the pipeline folder:
    ```bash
    cd DetectingSWRs/ABI_VisBehave_Pipeline
    ```

4. Ensure the config file, `abi_visbehave_swr_config.yaml`, is set to use the appropriate number of cores that your machine can handle.

5. Run the detection scripts in the following order:
    ```bash
    python abi_visbehave_swr_detector.py
    python abi_visbehave_filtering_swr_events_karlsson_detector.py
    python abi_visbehave_global_ripple_detector.py
    ```

6.  Use ctrl+b, d to exit the tmux session without killing it. It is recomended to check htop to ensure the server is behaving appropriately.

Note:  We have also created scripts for running the pipelines on slurm for shared computing clusters.  (Will be provided)

### Figures and Technical Validation

Contains notebooks to create the images in the Background & Summary as well as the Technical Validation section. Includes methods for visualizing the ripples and methods for visualizing probe position in brainrender. In the IBL validation notebook, there are also methods for plotting the CSD plots.

### Images

Images for the repo.

### PowerBandFilters

The code used to create the filters for the SWR detection pipelines.


![](Images/figure_one_v6.svg)
