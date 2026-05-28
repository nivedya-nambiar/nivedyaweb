---
layout: page
title: Projects
---
## Analysis of Corticospinal fMRI in Multisensory Integration within VR  
This year-long project was carried out at [MIP:Lab](https://miplab.epfl.ch/) under the supervision of Ekansh Sareen, Dr. Francesca Saviola, and Prof. Dimitri Van De Ville. The project focused on analysing corticospinal fMRI data collected during a multisensory integration task in virtual reality. The acquisition used a corticospinal sequence capable of capturing both the brain and cervical spinal cord within a single field of view, following the approach described by [Landelle et al.](https://doi.org/10.1162/imag_a_00284).

Participants experienced varying levels of visuo-tactile illusion while immersed in VR. I also assisted with participant recordings, which gave me hands-on experience with experimental setup and acquisition workflows — from marker placement for motion tracking to monitoring timing consistency, experimental conditions, and overall data quality across sessions. Tiny details become tyrants surprisingly quickly inside an MRI scanner.

### GLM Modelling
As with most fMRI studies, the analysis began with preprocessing: slice-timing correction, separation of cortical and spinal volumes, tissue segmentation, motion correction, physiological denoising, normalization to standard templates (MNI152 for cortex and PAM50 for spine), and smoothing.

We then optimized the GLM design to better capture task-related and low-frequency variation in the data. At the cortical level, we reproduced expected somatosensory activation during congruent visual and tactile stimulation. Spinal effects, however, were weaker and considerably more variable across participants; activation in the expected dorsal horn regions was not consistently observable, likely due to physiological variability and acquisition limitations.

The resulting beta maps identified the right temporo-parietal junction as a key region encoding visuo-tactile mismatch during illusion, consistent with prior [literature](https://doi.org/10.1016/j.plrev.2022.07.001). Spinal findings were evaluated using both parametric statistics and non-parametric [permutation testing](https://web.mit.edu/fsl_v5.0.10/fsl/doc/wiki/Randomise(2f)UserGuide.html), though interpretation remained challenging.

To further investigate cortical dynamics, we performed generalized psychophysiological interaction (gPPI) analyses to examine task-dependent functional connectivity between seed regions and the rest of the brain.

Most analyses related to the project were done using the [nilearn](https://nilearn.github.io/stable/index.html) library with the exception of permuation-based inference and gPPI analyses, for which we relied on [FSL](https://fsl.fmrib.ox.ac.uk/fsl/docs/).

### Corticospinal Gradients
As an extension of the project, we adapted cortical gradient-mapping frameworks such as those introduced by [Margulies et al.](https://doi.org/10.1073/pnas.1608282113) to include corticospinal connectivity — a first application of its kind. Functional gradients describe continuous spatial hierarchies between parcels based on similarity in connectivity patterns.

Using resting-state data, we identified principal and secondary gradients within the combined cortex–spine system that differed from canonical cortical gradient axes. Some selected findings from this work were later presented at ISBI 2026, where Ekansh gave an oral presentation. A follow-up manuscript is currently in preparation.

<br/>
![Cortical projection of the first 2 cortical and corticospinal gradient axes](https://github.com/nivedya-nambiar/nivedyaweb/blob/master/assets/corticospinal/cs_cortex_projection.png?raw=true "Cortical projection of the first 2 cortical and corticospinal gradient axes")
<br/>

We observed biologically consistent organization of resting-state spinal connectivity with clear level-dependent structure. Within spinal-level connectivity, the gradients reflected the butterfly-shaped anatomical organization of spinal parcels, as illustrated below.

<br/>
![The gradients computed for C4-C4 connectivity projected to the spine and visualized on a scatter plot](https://github.com/nivedya-nambiar/nivedyaweb/blob/master/assets/corticospinal/c4_grad_spinal.png?raw=true "The gradients computed for C4-C4 connectivity projected to the spine and visualized on a scatter plot")
<br/>

One major takeaway from this work was how strongly gradient results depend on the chosen parcellation scheme, and how important it is to align parcellation choices with the underlying hypothesis. For comparisons across connectivity matrices, we relied on Procrustes alignment to consistently align gradient axes.

### Cortico-spino-thalamic Gradients
We then extended the analysis to task-state gradients using a more targeted hypothesis-driven approach. Specifically, we investigated reorganization of the hierarchy spanning the somatosensory cortex, insula, thalamus, and spinal cord.

The insula was of particular interest because of its established role in saliency, interoception, and cognitive control — all highly relevant in an illusion-based paradigm involving manipulated sensory feedback. Participants also frequently reported emotional responses such as frustration when they detected mismatches between visual and tactile stimulation, making the region especially compelling to study.

The first stage of this project focused on insular gradients and how their functional organization changed across different illusion conditions. The report for this work is available [here](https://drive.google.com/file/d/1ENhen0YZM7xyM-XAd09dNWbgey-GCIei/view?usp=sharing).

## Validating EEG headset for cognitive load measurement
As part of my internship at Logitech's Technology Office, I'm working with their EEG headset prototype to test and validate the capabilities of this dry, low-density system for measuring abstract cognitive states such as overload, fatigue and focus.

## Preventing Workplace Accidents via Neural Signatures of Cognitive Overload
This project was supervised by Dr. Anna Custo at the [MySpace Lab](https://www.chuv.ch/en/neurosciences/dnc-home/recherche/centre-de-recherche-en-neurosciences/neurotech/research-labs/myspaceneurotech) in CHUV, working in collaboration with Lombardini22. Here, I worked on modelling cognitive overload using neural and physiological signals to investigate whether biomarkers derived from these signals could help detect fatigue and overload in real time to prevent workplace accidents.

The dataset consisted of lab-grade EEG recordings alongside heart rate and respiratory measurements collected while participants performed a dual-task paradigm designed to modulate working memory and attentional load.

My work focused on three main components:

1. Developing a performance metric that combined both tasks of the dual-task paradigm into a single measure sensitive to cognitive load modulation.
2. Performing statistical analyses to verify whether experimentally imposed difficulty levels were reflected in measurable changes in EEG, heart rate, and respiratory signals.
3. Implementing classification models that used neural and physiological features to predict participants’ cognitive load levels as reflected in their performance scores.

A major part of the project involved carefully validating the modelling pipeline to avoid overinterpreting results given the relatively small dataset size and the noisy, sparse nature of physiological recordings. We also explored participant stratification using self-assessment measures such as frustration and anxiety to better understand inter-subject variability.

## Decoding orientation of grating stimuli from fMRI data
This half-year long project aimed at building decoder models to classify the orientation of stimuli presented to subjects in a scanner, and was carried out at the [Cognition Lab](https://cns.iisc.ac.in/sridhar/) at the Indian Institute of Science, under the supervision of Prof. Sridharan Devarajan. I got the chance to plan and implement the full experimental workflow - from experiment design to implementing it with [Psychopy](https://psychopy.org/index.html) and finally recruiting subjects and acquiring task fMRI data to then decode the orientation from.

## Modelling biologically feasible classifiers with Liquid State Machines
During my bachelor studies, I worked with Liquid State Machines (LSMs) under the supervision of Anmol Biswas and Prof. Udayan Ganguly. The projects were preliminary focused on improving and testing the capability of these systems in classification problems and noise detection in speech. You can find a brief context for LSMs in the section below.

### Astrocyte Modulated Synaptic Plasticity in LSMs
Liquid state machines (LSMs) are a type of spking neural network (SNN), consisting of a reservoir of neurons with recurrent connections where communication across "synapses" ensues by means of spikes, quite similar to the biological nervous system. These networks are especially suited for problems involving time-series data like speech classifiation, owing to spike propagation through the reservoir over time and presence of recurrent connections to integrate past and present inputs into the decision making process. Unlike classical neural networks, the synaptic weights of LSMs are not modulated by backpropagation. Instead they could be modulated by spike timing dependent plasticity(STDP), a learning rule seen in biological networks, whereby the synaptic weight is increased inversely as the time taken for the postsynaptic spike after the presynaptic spike. The weight is decreased when postsynaptic neuron spikes before the presynaptic neuron. Several modifications to this rule have been proposed, fueled by better understanding of the working of the brain. Astrocytes have since long been heralded for their housekeeping roles within the nervous system, but their role in regulating synaptic transmission and functional synaptic plasticity has garnered attention in recent years. This serves as inspiration for the astrocyte-modulated synaptic plasticity rule proposed by [Ivanov et al](https://doi.org/10.48550/arXiv.2111.01760).  
<br/>
![Astrocytes in the Rat Brain](https://upload.wikimedia.org/wikipedia/commons/thumb/6/63/Astrocyte5.jpg/375px-Astrocyte5.jpg "Astrocyte cultured from rat brain tissue, source:Wikipedia")
<br/>
In this project, I implemented the rules proposed by  [Ivanov et al](https://doi.org/10.48550/arXiv.2111.01760) and introduced an additional modification in order to improve performance of the network. In the original rule, the astrocyte parameters were responsible for a modulation of only the synaptic depression rate. Instead I attempted to modulate the synaptic potentiation rate as well by means of one of the astrocyte parameters. An accuracy of 86.7% was attained on a speech classification problem on the TI-46 dataset.
<br/>
[Report](https://drive.google.com/file/d/1zmClc1iDENBjIH4hV0ymn1Ke9-FAgr1c/view?usp=sharing)

### Spiking Neurons for Filtering Noisy Speech
Additive noise degrades the performance of all kinds of speech classifiers, and liquid state machines (LSMs, see [previous project desc.] (#Astrocyte Modulated Synaptic Plasticity in LSMs)) are affected by how this noise manifests as unwanted spikes in the input layer and as distortions of the spiking pattern of speech. Through this project, I have attempted to develop a mechanism by which the input layer spikes are gated in time to pass the spikes only at instants where speech is detected. The overarching assumption here is that simpler kinds of noise - with uniform and predictable waveforms - do not create significant distortion in speech, making them easier to gate off. The basic objective is filtering away the noise, which ideally involves retaining those spikes in the input that would have been present had only the original speech signal been passed, and ignoring the spikes resulting from noise. A primary step toward this is gating in time, i.e., detecting the presence of speech at a time instant, and then have the liquid “listen” only at these instants. This approach essentially is equivalent to voice activity detection in the presence of noise. The performance of the liquid can be tested after validating that this approach “works”. In this project, the gating was verified through visual inspection of the waveforms, as described in the methods section of the report (link below).
<br/>
![Schematic of proposed spiking network](https://github.com/nivedya-nambiar/nivedyaweb/blob/master/assets/btp2/gating2SFA_scheme_crop.jpg?raw=true "Schematic of the proposed spiking network for gating noisy speech")
<br/>
[Report](https://drive.google.com/file/d/1SAtwfhetLKOEs4O0_PheLeT7EGBxuB-F/view?usp=sharing)

### Multimodal Neurons in LSMs
Multimodal neurons in LSMs are expected to combine data from different modalities simultaneously to produce a better informed classification output. This is biologically plausible as the human brain indeed uses inputs from audio, visual and tactile sensors to distinguish and classify objects in the real world. Previously, [Rathi et al](https://ieeexplore.ieee.org/document/8482490) proposed an architecture for multimodal LSMs that includes excitatory connections between neurons in the visual “cortex” and the auditory “cortex”, and these cross-modal connections improved the performance of the LSM. In this project I worked in a team of 3 to model our LSM after this same architecture of cross modal connections between auditory and visual parts of the neuron reservoir for spoken/handwritten digit classification.
<br/>
[Report](https://drive.google.com/file/d/1SUWirFBMb4tlUpdv5eX0aPlEw_y4OINf/view?usp=sharing)
