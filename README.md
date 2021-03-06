# Spectra
<p align="justify">
Spectra is an image processing algorithm designed to detect scenes, similarity, and blur in time ordered image databases. The algorithm is capable of categorizing images by scene and giving suggestions to the user to review and delete similar and or blurry images.<br><br>Spectra operates completely offline and creates <code>.spectra_data</code> and <code>.spectra_temp</code> files in every directory analyzed in order to speed up the analysis of that directory in the future.<br><br>Spectra currently supports JPG, JPEG, PNG, and TIFF file formats.
</p>

## Compatibility
<p align="justify">
Spectra is officially compatible with macOS and popular Linux distributions in a python3 environment.
</p>

## Dependencies
<p align="justify">
Spectra requires several dependencies to operate as a command line utility. You must have the latest version of <code>python3</code> and <code>pip3</code> installed on your computer to use the program. You will also need to install the latest packages of PIL, shutil, cv2, imagehash, numpy, scipy, skimage, and sklearn. These packages should be setup automatically by the installation script that is included with this repository, so its not necessary to manually install all of them.
</p>

## Installation

#### Downloading Spectra
<p align="justify">
Please navigate to the <a href="https://github.com/nalinahuja22/spectra/releases">release</a> tab of this repository and download the latest version of this project. You can perform this download within a browser environment or using a command line utility like <code>wget</code> or <code>curl</code>. Alternatively, you can clone this <a href="https://github.com/nalinahuja22/spectra">repository</a> but it is recommended that you download the most recent release as the git repository is comparatively larger.
</p>

#### Installing Spectra
<p align="justify">
Then, navigate to the location where the Spectra repository contents have been downloaded onto your machine and run the <a href="https://github.com/nalinahuja22/spectra/blob/master/install_spectra">install_spectra</a> installation script. This executable will install Spectra in a hidden directory called <code>~/.spectra</code> and install all the dependencies required by Spectra, assuming that you have <code>python3</code> and <code>pip3</code> installed on your machine. When the installation script finishes, source your terminal profile and restart your terminal to fully configure the installation.<br><br>If you would like to do a manual installation of Spectra, all you need to do is move the repository contents you downloaded, besides the <a href="https://github.com/nalinahuja22/spectra/blob/master/install_spectra">install_spectra</a> file, into a folder at <code>~/.spectra</code> which you will have to create yourself. Then source and restart your terminal profile after adding the following command to your terminal profile.
</p>

```bash
function spectra() {
  command python3 ~/.spectra/bin/spectra.py "$@"
}
```

## Usage
<p align="justify">
Spectra takes up to four input values. The image path is the only required argument to run the script and must always be the first argument passed to Spectra. The sensitivity flags on the other hand are optional and can be indicated in any order to Spectra. It is not necessary to indicate the sensitivity thresholds since there are default values for them internally that work for most image repositories. However, if you need to indicate a sensitivity threshold, you can simpily indicate the flag and the sensitivity expressed as a percentage from 0 to 100, where 100 percent sensitivity results in the most sensitive image processing.
</p>

```bash
command spectra <path> <-b blur_sensitivity> <-s scene_sensitivity> <-d duplicate_sensitivity>
```
