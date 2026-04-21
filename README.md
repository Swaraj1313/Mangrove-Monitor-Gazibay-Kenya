# Mangrove-Monitor-Gazibay-Kenya
[🌿 Open Monitor on App](https://swaraj1313.users.earthengine.app/view/mangrove-monitor-gazibay-kenya)

## Will take a few moments for the layers to upload (click Layers and check layers from the dropdown)

## Overview
Developed a geospatial tracking architecture using Supervised Machine Learning (Random Forest). The model was trained on engineered spectral features (NDVI, NDWI) extracted from multispectral satellite imagery to autonomously classify coastal land-cover and quantify decadal ecological shifts to quantify decadal mangrove depletion and conservation recovery (2014–2025) in Gazi Bay, Kenya. The approach can be applied to other areas as well. For example, in agriculture, similar models can be trained to distinguish between crops grown in the same season (such as wheat, mustard, chickpea, and barley), helping estimate crop-wise sown area in hectares.

Mangroves are hard to identify in satellite images because they look very similar to other green vegetation. From above, mangroves, forests, and even some wetland plants can all appear as dense green cover, so a normal satellite image cannot easily tell them apart.

To solve this, a machine learning method called Random Forest was used. Instead of just looking at how green things appear in regular photos, the model was trained to recognize different types of land—mangroves, other vegetation, water, and bare land—by analyzing how they reflect different types of light.

Satellite sensors capture not just visible light, but also infrared wavelengths that our eyes can't see. Different surfaces reflect these wavelengths differently: healthy vegetation strongly reflects near-infrared light, while water absorbs it. 

The model was trained using two key indicators calculated from these reflections:

NDVI (Normalized Difference Vegetation Index) – measures how healthy and green the vegetation is by comparing red and near-infrared light reflection & NDWI (Normalized Difference Water Index) – measures water content by comparing green and near-infrared light reflection
Mangroves have a unique "spectral signature"—they reflect light in a specific pattern because they're both dense vegetation AND constantly surrounded by water. By learning to recognize this distinct reflection pattern across different wavelengths, the model can distinguish mangroves from ordinary land-based trees or wetland vegetation, even when they look similar in regular color images.


## AI & Machine Learning Architecture
* **Algorithm:** Supervised Random Forest Classifier (100 decision trees).
* **Feature Engineering:** Trained on multi-dimensional spectral signatures, combining standard optical bands with custom moisture and vegetation indices (NDWI, NDVI) derived from Landsat 8 and 9 Surface Reflectance data.
* **Autonomous Classification:** The model successfully isolates intertidal mangroves from inland terrestrial forests, bare earth, and estuarine water, stripping out the "noise" common in basic thresholding methods.

## Scalability & Generalization

* **Temporal Transferability:** Rather than fitting separate, biased models for different years, a single classifier learns the fundamental spectral fingerprint of the ecosystem. This unified AI autonomously classifies unseen imagery across a 10-year temporal gap, ensuring a mathematically rigorous "apples-to-apples" comparison.
* **Geographic Scalability:** Because the model relies on normalized planetary data (Landsat Collection 2) and physics-based spectral indices rather than hardcoded visual filters, the underlying architecture can be easily generalized to track intertidal ecosystems in other coastal regions globally.

## Key Capabilities
* **Decadal Change Detection:** Programmatically subtracts temporal models to generate exact, pixel-by-pixel Loss (Depletion) and Gain (Conservation Recovery) visualizations.
* **Impact Verification:** Provides quantitative, unbiased verification for local conservation and carbon-credit initiatives.

## Generalizability

The underlying methodology is transferable and can be adapted to:

- Coastal ecosystem monitoring (mangroves, wetlands, salt marshes)  
- Deforestation and afforestation tracking  
- Urban expansion and land-use change  
- Agricultural transitions and cropping patterns by trainig model for identifieng different crops. 
- Floodplain and water body dynamics

- ## Platform

All processing is executed within **Google Earth Engine**, enabling:

- Scalable analysis over large geographies  
- No local data storage requirements  
- Rapid prototyping and deployment of geospatial AI models

- ## Visual Outputs

### 2015 False Color
![2015](images/2015_false_color.png)

### 2025 False Color
![2025](images/2025_false_color.png)

### Mangrove Change (Gain/Loss)
![Change](images/mangroves_gain_loss.png)

### ESA Comparison
![ESA](images/esa_layover.png)

