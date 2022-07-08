[![home](https://img.shields.io/badge/gears-home-blue?style=flat)](../../..)
[![examples](https://img.shields.io/badge/gears-examples-green?style=flat)](../..)
[![physics](https://img.shields.io/badge/physics-processes-red?style=flat)](..)

Muons, being charged particles (mu+ and mu-), interact with matter by ionizing it. They themselves lose energy during this process.

### Stopping power

The stopping power of a material to a particle is defined as the energy loss in a unit track length, _S = -dE/dx_. It changes with material, particle type, and the kinetic energy of the particle. The [first figure](https://pdg.lbl.gov/2022/web/viewer.html?file=../figures/passage/figures/rpp_icru49_cu_col.pdf) in the [PDG][] [review][] on [Passage of particles through matter](https://pdg.lbl.gov/2022/reviews/rpp2022-rev-passage-particles-matter.pdf) shows the *dE/dx* of muons in Cu as a function of their energies. It reaches its minimum around 1 GeV.

## Cosmic ray muons
According to [HyperPhysics][], the average energy of muons reaching sea level is about 4 GeV. They are called [minimum ionizing particles][mip], as their [dE/dx in air](https://pdg.lbl.gov/2022/web/viewer.html?file=../figures/passage/figures/dedx_table_98.pdf) is around its minimum . A muon loses about 2 GeV passing through the atmosphere, its original energy is then about 6 GeV.

### Scintillating panels

<a href="http://physino.xyz/gears/examples/physics/muon/panels.html"><img align="right" width="120px" src="panels.png"/></a>

[panels.tg](panels.tg) contains a portion of a plastic scintillation panel. [panels.mac](panels.mac) shoots 6 GeV mu+ to it. The simulation result is saved in a ROOT file [panels.root](https://drive.google.com/file/d/1cnNmpTQE_vNGnnvs69aLsdNQHyFfeypM/view?usp=sharing).

### dE/dx plot

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/jintonic/gears/HEAD?labpath=examples%2Fphysics%2Fmuon%2Fdedx.ipynb)
[![CoLab](https://img.shields.io/badge/Google-CoLab-red?style=flat)](https://colab.research.google.com/github/jintonic/gears/blob/master/examples/physics/muon/dedx.ipynb)

The [GEARS output](../../output#step-point) provides two variables to roughly calculate this: _de_ and _dl_. _de_ is the energy deposited in a step point. _dl_ is the corresponding step length. A jupyter notebook [dedx.ipynb](dedx.ipynb) is created to analyze the cosmic ray muon dE/dx in air and the scintillation panels. It can be run in a web browser through [binder][] or Google [CoLab][].

[mip]: https://pdg.lbl.gov/2022/web/viewer.html?file=../figures/passage/figures/rpp_icru49_cu_col.pdf
[HyperPhysics]: http://hyperphysics.phy-astr.gsu.edu/hbase/Particles/muonatm.html
[PDG]: https://pdg.lbl.gov
[review]: https://pdg.lbl.gov/2022/reviews
[binder]: https://mybinder.org/v2/gh/jintonic/gears/HEAD?labpath=examples%2Fphysics%2Fmuon%2Fdedx.ipynb
[CoLab]: https://colab.research.google.com/github/jintonic/gears/blob/master/examples/physics/muon/dedx.ipynb