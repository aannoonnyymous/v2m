---
layout: default
title: "Diff-V2M: A Hierarchical Conditional Diffusion Model with Generalizable Rhythmic Modeling for Video-to-Music Generation"
---
<style>
/* 修改页面主标题字体大小 */
.project-name {
  font-size: 36px !important;
  max-width: 1200px;
  margin: auto;
  text-align: center;
  word-break: break-word;
}
.main-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}
</style>


## Abstract
We propose Diff-V2M, a generalizable video-to-music generation framework based on a hierarchical conditional diffusion model. We begin by evaluating several rhythmic representations applicable across different video domains, including low-resolution mel-spectrograms, low-resolution tempograms, and quantized onset detection functions (ODF), and observe the quantized ODF demonstrates superior cross-domain adaptability. Built upon these insights, Diff-V2M consists of two main components: a feature extraction module and a conditional music generation module. Emotional, semantic, and rhythmic features are extracted from video inputs and incorporated into the generator via a hierarchical cross-attention mechanism, providing rich and temporally aligned conditioning signals. To further enhance feature integration, we introduce a novel timestep-aware feature-wise linear modulation (FiLM) mechanism along with a set of feature fusion strategies, enabling the model to adaptively prioritize and combine semantic and rhythmic cues based on the diffusion timestep. Extensive experiments demonstrate that Diff-V2M outperforms existing models on both in-domain datasets and the out-of-domain V2M-Bench dataset, achieving superior performance in terms of objective metrics and subjective comparisons.
Demos are available at [here](https://aannoonnyymous.github.io/v2m/).

## Comparisons with SOTA
<h3 align="center" style="color: black; font-weight: bold;">BGM909 Test Dataset/h3>

<table>
  <thead>
    <tr>
      <th>Diff-V2M (ours)</th>
      <th>VidMuse</th>
      <th>GVMGen</th>
      <th>MuMu-LLaMA</th>
      <th>Video2Music</th>
      <th>CMT</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><video width="250" controls><source src="video/BGM-demo/212_7.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/212_7-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/212_7-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/212_7-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/212_7-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/212_7-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>
    
    <tr>
      <td><video width="250" controls><source src="video/BGM-demo/103_13.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/103_13-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/103_13-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/103_13-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/103_13-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/103_13-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>

    <tr>
      <td><video width="250" controls><source src="video/BGM-demo/88_3.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/88_3-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/88_3-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/88_3-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/88_3-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/88_3-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>

    <tr>
      <td><video width="250" controls><source src="video/BGM-demo/180_4.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/180_4-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/180_4-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/180_4-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/180_4-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/180_4-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>

    <tr>
      <td><video width="250" controls><source src="video/BGM-demo/600_11.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/600_11-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/600_11-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/600_11-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/600_11-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="video/BGM-demo/600_11-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>
  </tbody>
</table>

<h3 align="center" style="color: black; font-weight: bold;">SymMV Test Dataset</h3>

<table>
  <thead>
    <tr>
      <th>Diff-V2M (ours)</th>
      <th>VidMuse</th>
      <th>GVMGen</th>
      <th>MuMu-LLaMA</th>
      <th>Video2Music</th>
      <th>CMT</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><video width="250" controls><source src="videos/diff-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/vidmuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/gvmgen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/mumu-llama.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/video2music.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/cmt.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>
    <tr>
      <td><video width="250" controls><source src="videos/diff-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/vidmuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/gvmgen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/mumu-llama.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/video2music.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/cmt.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>
  </tbody>
</table>

<h3 align="center" style="color: black; font-weight: bold;">V2M-Bench Test Dataset</h3>

<table>
  <thead>
    <tr>
      <th>Diff-V2M (ours)</th>
      <th>VidMuse</th>
      <th>GVMGen</th>
      <th>MuMu-LLaMA</th>
      <th>Video2Music</th>
      <th>CMT</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><video width="250" controls><source src="videos/diff-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/vidmuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/gvmgen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/mumu-llama.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/video2music.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/cmt.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>
    <tr>
      <td><video width="250" controls><source src="videos/diff-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/vidmuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/gvmgen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/mumu-llama.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/video2music.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="250" controls><source src="videos/cmt.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>
  </tbody>
</table>

## More Samples Generated by Diff-V2M
<table>
  <tr>
    <td>
      <video width="345" controls>
        <source src="videos/video1.mp4" type="video/mp4">
      </video>
    </td>
    <td>
      <video width="345" controls>
        <source src="videos/video2.mp4" type="video/mp4">
      </video>
    </td>
    <td>
      <video width="345" controls>
        <source src="videos/video3.mp4" type="video/mp4">
      </video>
    </td>
  </tr>
  <tr>
    <td>
      <video width="345" controls>
        <source src="videos/video4.mp4" type="video/mp4">
      </video>
    </td>
    <td>
      <video width="345" controls>
        <source src="videos/video5.mp4" type="video/mp4">
      </video>
    </td>
    <td>
      <video width="345" controls>
        <source src="videos/video6.mp4" type="video/mp4">
      </video>
    </td>
  </tr>
  <tr>
    <td>
      <video width="345" controls>
        <source src="videos/video4.mp4" type="video/mp4">
      </video>
    </td>
    <td>
      <video width="345" controls>
        <source src="videos/video5.mp4" type="video/mp4">
      </video>
    </td>
    <td>
      <video width="345" controls>
        <source src="videos/video6.mp4" type="video/mp4">
      </video>
    </td>
  </tr>
</table>

