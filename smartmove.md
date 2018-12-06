class: center, middle

# Neural network classification of harp seal body density

## Ryan J. Dillon

[ ](https://cicero.xyz/v3/remark/0.14.0/github.com/ryanjdillon/pres_smartmove/master/smartmove.md)

---

## The idea

Hydrodynamic model (*Miller et al., 2015*)

<img src="img/miller_equation.png" style="height: 400px;">

---

## Overview

<img src="img/smartmove_diagram.png" style="height:400px;">

---

## Study Area

**Kaldfjord, Norway** (just outside of Tromsø)

<img src="img/study_area_composite.png" style="height:400px;">

---

## Field experiments

- Weights and floats attached to seals to simulate changes in body density

<img src="http://bergen.ryandillon.net/coexist/seal.jpg" style="height:400px;">

---

Used Power Spectral Density plots to determing filter cutoff frequency
<img src="img/glide_psd_zoom.png" style="height:200px;">

Example of filtered signal
<img src="img/glide_acc-plot_zoom.png" style="height:200px;">

---

Glides auto-detected:
- rate of accent (from depth sensor)
- stroke frequency (under specified frequency animal is gliding)
- Glides subdivided to 2second intervals

<img src="img/subglide_highlight.png" style="height: 300px;">

---

## Accuracy

### 84.8%

Model selected on classification accuracy on unseen test set

<img src="img/confusion-matrix.png" style="height: 300px;">

---

## Effect of Hyperparameters

The only hyperparameters that affected accuracy wereL
- # of hidden nodes
- # of hidden layers

<img src="img/hyperparameter_accuracy.png" style="height: 300px;">

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
Library for DSP of marine mammal telemetry and data logger data. [Github](https://github.com/ryanjdillon/pyotelem)

**pylleo**
Calibrate and restructure accelerometry and data logger data. [Github](https://github.com/ryanjdillon/pylleo)

<img src="img/calibration_app.png" style="height: 300px;">

---

# Thank you! Questions?
