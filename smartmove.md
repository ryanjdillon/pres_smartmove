class: center, middle

# Neural network classification of harp seal body density

## Ryan J. Dillon

[ ](https://cicero.xyz/v3/remark/0.14.0/github.com/ryanjdillon/pres_smartmove/master/smartmove.md)

---

## The idea

Hydrodynamic model (*Miller et al., 2015*)

<img src="img/miller_equation.png" style="height: 100px; block; margin-left: auto; margin-right: auto;">

---

## Overview

<img src="img/smartmove_diagram.png" style="height:500px; block; margin-left: auto; margin-right: auto;">

---

## Study Area

**Kaldfjord, Norway** (just outside of Tromsø)

<img src="img/study_area_composite.png" style="height:400px; block; margin-left: auto; margin-right: auto;">

---

## Field experiments

- Weights and floats attached to seals to simulate changes in body density

<img src="http://bergen.ryandillon.net/coexist/seal.jpg" style="height:400px; block; margin-left: auto; margin-right: auto;">

---

Used Power Spectral Density plots to determing filter cutoff frequency

<img src="img/glide_psd_zoom.png" style="height:300px; block; margin-left: 0;">

Example of filtered signal

<img src="img/glide_acc-plot_zoom.png" style="height:300px; block; margin-right: 0;">

---

Glides auto-detected:
- Rate of accent (from depth sensor)
- Stroke frequency (under specified frequency animal is gliding)
- Glides subdivided to 2second intervals

<img src="img/subglide_highlight.png" style="height: 450px; block; margin-left: auto; margin-right: auto;">

---

## Accuracy

### 84.8%

Model selected on classification accuracy on unseen test set

<img src="img/confusion-matrix.png" style="height: 400px; block; margin-left: auto; margin-right: auto;">

---

## Effect of Hyperparameters

The only hyperparameters that affected accuracy wereL
- \# of hidden nodes
- \# of hidden layers

<img src="img/hyperparameter_accuracy.png" style="height: 300px; block; margin-left: auto; margin-right: auto;">

---

## Open code and data

**Install**

```bash
pip install git@github.com:ryanjdillon/smartmove.git
```

**Usage**

```python
import smartmove
smartmove.create_project('./')

# Now copy Little Leo data to `data_tag`, csv data to `data_csv`, and CTD data to `data_ctd`
# Then...

# Setup your analysis helper
anl = smartmove.Analysis('./')

# Run the glide identification
anl.run_glides()

# Run the ANN training
anl.run_ann()

# Make the figures and tables for the paper
anl.make_tables()
anl.make_figures()
```

---

## Ancillary code developed

**pyotelem**
Library for DSP of marine mammal data logger data. [Github](https://github.com/ryanjdillon/pyotelem)

**pylleo**
Calibrate and restructure accelerometry and data logger data. [Github](https://github.com/ryanjdillon/pylleo)

<img src="img/calibration_app.png" style="height: 450px; block; margin-left: auto; margin-right: auto;">

---



## Thank you! Questions?
