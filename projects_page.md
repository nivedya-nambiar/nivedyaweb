---
layout: page
title: Projects
---
# Table of Contents
1. [Astrocyte Modulated Synaptic Plasticity in LSMs](##Astrocyte Modulated Synaptic Plasticity in LSMs)
2. [Spiking Neurons for Filtering Noisy Speech](##Spiking Neurons for Filtering Noisy Speech)
3. [Multimodal Neurons in LSMs](##Multimodal Neurons in LSMs)

## Astrocyte Modulated Synaptic Plasticity in LSMs
Liquid state machines (LSMs) are a type of spking neural network (SNN), consisting of a reservoir of neurons with recurrent connections where communication across "synapses" ensues by means of spikes, quite similar to the biological nervous system. These networks are especially suited for problems involving time-series data like speech classifiation, owing to spike propagation through the reservoir over time and presence of recurrent connections to integrate past and present inputs into the decision making process. Unlike classical neural networks, the synaptic weights of LSMs are not modulated by backpropagation. Instead they could be modulated by spike timing dependent plasticity(STDP), a learning rule seen in biological networks, whereby the synaptic weight is increased inversely as the time taken for the postsynaptic spike after the presynaptic spike. The weight is decreased when postsynaptic neuron spikes before the presynaptic neuron. Several modifications to this rule have been proposed, fueled by better understanding of the working of the brain. Astrocytes have since long been heralded for their housekeeping roles within the nervous system, but their role in regulating synaptic transmission and functional synaptic plasticity has garnered attention in recent years. This serves as inspiration for the astrocyte-modulated synaptic plasticity rule proposed by [Ivanov et al](https://doi.org/10.48550/arXiv.2111.01760).  
<br/>
![Astrocytes in the Rat Brain](https://upload.wikimedia.org/wikipedia/commons/thumb/6/63/Astrocyte5.jpg/375px-Astrocyte5.jpg "Astrocyte cultured from rat brain tissue, source:Wikipedia")
<br/>
In this project, I implemented the rules proposed by  [Ivanov et al](https://doi.org/10.48550/arXiv.2111.01760) and introduced an additional modification in order to improve performance of the network. In the original rule, the astrocyte parameters were responsible for a modulation of only the synaptic depression rate. Instead I attempted to modulate the synaptic potentiation rate as well by means of one of the astrocyte parameters. An accuracy of 86.7% was attained on a speech classification problem on the TI-46 dataset.
<br/>
[Report](https://github.com/nivedya-nambiar/nivedyaweb/blob/master/assets/btp1/btp_report_190070039.pdf)

## Spiking Neurons for Filtering Noisy Speech
Additive noise degrades the performance of all kinds of speech classifiers, and liquid state machines (LSMs, see [previous project desc.] (#Astrocyte Modulated Synaptic Plasticity in LSMs)) are affected by how this noise manifests as unwanted spikes in the input layer and as distortions of the spiking pattern of speech. Through this project, I have attempted to develop a mechanism by which the input layer spikes are gated in time to pass the spikes only at instants where speech is detected. The overarching assumption here is that simpler kinds of noise - with uniform and predictable waveforms - do not create significant distortion in speech, making them easier to gate off. The basic objective is filtering away the noise, which ideally involves retaining those spikes in the input that would have been present had only the original speech signal been passed, and ignoring the spikes resulting from noise. A primary step toward this is gating in time, i.e., detecting the presence of speech at a time instant, and then have the liquid “listen” only at these instants. This approach essentially is equivalent to voice activity detection in the presence of noise. The performance of the liquid can be tested after validating that this approach “works”. In this project, the gating was verified through visual inspection of the waveforms, as described in the methods section of the report (link below).
<br/>
![Schematic of proposed spiking network](https://github.com/nivedya-nambiar/nivedyaweb/blob/master/assets/btp2/gating2SFA_scheme_crop.jpg?raw=true "Schematic of the proposed spiking network for gating noisy speech")
<br/>
[Report](https://github.com/nivedya-nambiar/nivedyaweb/blob/master/assets/btp2/report_190070039.pdf)

## Multimodal Neurons in LSMs
Multimodal neurons in LSMs are expected to combine data from different modalities simultaneously to produce a better informed classification output. This is biologically plausible as the human brain indeed uses inputs from audio, visual and tactile sensors to distinguish and classify objects in the real world. Previously, [Rathi et al](https://ieeexplore.ieee.org/document/8482490) proposed an architecture for multimodal LSMs that includes excitatory connections between neurons in the visual “cortex” and the auditory “cortex”, and these cross-modal connections improved the performance of the LSM. In this project I worked in a team of 3 to model our LSM after this same architecture of cross modal connections between auditory and visual parts of the neuron reservoir for spoken/handwritten digit classification.
<br/>
[Report](https://github.com/nivedya-nambiar/nivedyaweb/blob/master/assets/multimodal/Group2_stage2Report.pdf)
