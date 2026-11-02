## Paul-Adrian Gogîță

Computational physicist. Ph.D. candidate at the Doctoral School of Physics, University of Bucharest,
and research assistant at the Institute of Space Science (ISS — INFLPR subsidiary), Măgurele.

My research focuses on heavy-tailed statistics and stochastic modeling in complex systems, with
published work across currency-market, space-weather and environmental time series. I use
waiting-time distributions as a non-parametric observable to characterize and compare dynamical
regimes across disparate physical and empirical records. Methodologically, I develop open-source
scientific software in Julia—primarily multi-vendor GPU kernels and streaming data pipelines.

Current projects: gravitational-wave parameter estimation and deep-space telemetry simulation for
the LISA collaboration; GPU-accelerated N-body star-cluster simulation campaigns; statistical
computation in encrypted regime for TRUSTEE (Horizon Europe); ELI-RO eTARGET. Previously, I spent
three years at RATEN–CITON conducting probabilistic safety assessments (PSA) for nuclear facilities,
specializing in atmospheric dispersion modeling, Monte Carlo radiation transport, and
accident-frequency quantification.

Julia has been my primary language since 2018.

### Software

Maintained Julia packages with test suites, continuous integration and documentation; research
packages include citation metadata. All public and under active development.

**Gravitational waves and LISA telemetry**

| | |
|---|---|
| [CurvatureDistinguishability.jl](https://github.com/PaulGoG/CurvatureDistinguishability.jl) | Quartic distinguishability law for space-based gravitational-wave interferometry: the noise-weighted distance between a two-source signal and its best single-source template grows as the fourth power of the parameter separation, with the extrinsic curvature of the waveform manifold as coefficient; confusion-zone maps in parameter space. GPU kernels portable across CUDA, ROCm, oneAPI and Metal from a single source. Computational basis of the manuscript under revision at *Classical and Quantum Gravity*. |
| [StreamingInference.jl](https://github.com/PaulGoG/StreamingInference.jl) · [MilliHertzBase.jl](https://github.com/PaulGoG/MilliHertzBase.jl) · [MilliHertzQML.jl](https://github.com/PaulGoG/MilliHertzQML.jl) | Three layers for LISA telemetry. Windowed analysis of time series delivered in batches, late, out of order and with gaps: scheduling, conditioning, an estimator interface, evaluation. The gravitational-wave layer: noise models, IMRPhenomA waveforms, detector response, LISA Data Challenge products. A variational quantum classifier with data re-uploading for massive black hole binary coalescences, scored window by window on LDC Sangria data, completed or streamed through a simulated downlink, and evaluated against a classical baseline on the same features; a Julia port and operational extension of the method of Isfan et al., *Class. Quantum Grav.* **42**, 225001 (2025). |
| [DeepSpaceTelemetry.jl](https://github.com/PaulGoG/DeepSpaceTelemetry.jl) | Discrete-event simulator of deep-space mission telemetry: duty-cycled contact windows, a Gilbert–Elliott channel, FIFO live and LIFO archive routing, alert-latency metrology. Mission-agnostic core, LISA as the shipped scenario. |

**Complex systems and time series**

| | |
|---|---|
| [WaitingTimes.jl](https://github.com/PaulGoG/WaitingTimes.jl) | Exact waiting-time distributions of scalar time series over threshold grids, with verified accelerated kernels, GPU backends and provenance-tracked data products; computational framework for the two complex-systems publications below. |
| [MarketTickStreamer.jl](https://github.com/PaulGoG/MarketTickStreamer.jl) | Provider-agnostic tick-by-tick market data acquisition: live WebSocket streaming, historical REST backfill, vendor day-file import, an append-only raw layer, compaction to CSV or Arrow, and paced replay that returns the same channel type as the live source, so real-time methods can be developed offline. |

**Stellar dynamics**

| | |
|---|---|
| [Nbody6Dynamics.jl](https://github.com/PaulGoG/Nbody6Dynamics.jl) · [Nbody6PPGPU-beijing](https://github.com/PaulGoG/Nbody6PPGPU-beijing) | Nbody6++GPU star-cluster simulations from one configuration file: engine build with CUDA architecture detection, single-cluster and multi-cluster merger initial conditions, MPI launch and supervision across queue segments, post-processing of every standard output file, figures and animations. The fork carries the engine corrections the package builds on. |

**Nuclear physics and radiological safety**

| | |
|---|---|
| [AtmosphericDispersion.jl](https://github.com/PaulGoG/AtmosphericDispersion.jl) | Gaussian-plume dispersion, depletion, deposition and resuspension of radioactive stack releases over Pasquill–Gifford stability classes and a wind rose, every parameterisation asserted against its published source. A refactored Julia implementation of my 2021 B.Sc. codebase with benchmarked numerical corrections. |
| [DeterministicSequentialEmission.jl](https://github.com/PaulGoG/DeterministicSequentialEmission.jl) · [FissionFragmentsDomain.jl](https://github.com/PaulGoG/FissionFragmentsDomain.jl) | Prompt neutron emission from fission fragments, solved sequence by sequence from the energy balance of every split, and the fragmentation domain that prompt-emission and excitation-energy-partition models share. |
| [FissionTemperatureRatio.jl](https://github.com/PaulGoG/FissionTemperatureRatio.jl) · [ExforFissionData.jl](https://github.com/PaulGoG/ExforFissionData.jl) | The temperature-ratio extraction of the EPJ A paper below, from measured prompt neutron multiplicity with no emission model entering, and provenance-tracked retrieval of fission observables from the IAEA EXFOR archive. |

**Working tools**

| | |
|---|---|
| [scicomp-toolbox](https://github.com/PaulGoG/scicomp-toolbox) | Scientific scripting workbench: cross-vendor accelerator and host-processor diagnostics through one KernelAbstractions kernel, their figures, and workspace utilities behind one dispatcher, test runner and formatting gate. |
| [SshDataBridge.jl](https://github.com/PaulGoG/SshDataBridge.jl) · [SshAutoLogin.jl](https://github.com/PaulGoG/SshAutoLogin.jl) | Deployment of simulation codes to several compute nodes and harvesting of their results over SSH and rsync, and multi-session terminal login. Credentials never reach an argument vector, an environment, or `ps`. |
| [UniBuc-Computational-Physics-Coursework](https://github.com/PaulGoG/UniBuc-Computational-Physics-Coursework) | Six years of physics coursework translated from C, C++ and Octave into Julia, published together with a line-level defect census of the original student code. |

### Publications

- P.-A. Gogîță, T.-G. Dumitru, F.-I. Constantin, T.-A. Diac, A.-F. Neagoe, M.-C. Raportaru and
  A. Nicolin-Żaczek, *Scale-free to Pareto–Tsallis transitions in the distributions of waiting times:
  weather, sea-level, currency trading and automotive datasets*, **J. Phys. Complex. 7**, 035007
  (2026). [doi:10.1088/2632-072X/ae8aa5](https://doi.org/10.1088/2632-072X/ae8aa5)
- G. T. Pană, P.-A. Gogîță and A. Nicolin-Żaczek, *Waiting times for sea level variations in the Port
  of Trieste: a computational data-driven study*, **Rom. J. Phys. 69**, 111 (2024).
  [doi:10.59277/RomJPhys.2024.69.111](https://doi.org/10.59277/RomJPhys.2024.69.111)
- A. Tudora and P. Gogîță, *Temperature ratio `R_T = T_L/T_H` of fully accelerated complementary
  fragments (used for TXE partition) obtained independently of prompt emission model calculations*,
  **Eur. Phys. J. A 60**, 190 (2024).
  [doi:10.1140/epja/s10050-024-01375-7](https://doi.org/10.1140/epja/s10050-024-01375-7)
- C. V. Ionescu, P.-A. Gogîță, L. I. Caramete and A. Caramete, *Geometric distinguishability of
  two-source gravitational-wave signals from the extrinsic geometry of the single-source waveform
  manifold*. Submitted to *Classical and Quantum Gravity*; under revision.

ORCID [0009-0007-6716-165X](https://orcid.org/0009-0007-6716-165X) · LinkedIn [paul-adrian-gogita](https://www.linkedin.com/in/paul-adrian-gogita/)

### Tools

Julia · C/C++ · Fortran · GPU kernels portable across CUDA, ROCm, oneAPI and Metal through
KernelAbstractions.jl · MPI and OpenMP · Docker · Linux (Fedora) · LaTeX
