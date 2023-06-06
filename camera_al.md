---
title: "Recognition of Camera Angle and Camera Level in Movies from Single Frames"
subtitle: 
layout: page
show_sidebar: false
hero_image: /img/header.png
---

<!-- #region -->
# Camera Feature Recognition

## What is the aim?
<div class="columns is-mobile is-centered is-vcentered">
  <div class="column is-4">
    <span>
    The position and orientation of the camera in relation to the subject(s) in a movie scene, namely level and camera angle, are essential features in the film-making process due to their influence on the viewer's perception of the scene.
Here, we propose to use Convolutional Neural Networks (CNNs) for the task of automatic recognition in movie frames of the camera angle (amongst five classes: Overhead, High, Neutral, Low, and Dutch) and camera level (amongst Aerial, Eye, Shoulder, Hip, Knee, and Ground).
The developed models, the annotation tool, and frame data are made available  for a wide range of research purposes, such as movie stylistic analysis, video recommendation, and media psychology.
    </span>
  </div>
  <div class="column">
    <img src="/img/angle-scale-examples.png">
  </div>
</div>

[Paper (Soon)](/#TBD){: .button}

<!-- #endregion -->

## Dataset 

<!-- #region -->
For the aim of this work, we annotate camera angle on five different classes: Overhead, High, Neutral, Low, Dutch, as shown
in Figure 1 (first row). The angle class describes camera rotation along both lateral (High, Neutral, and Low) and longitudinal (Dutch) axes. 
In particular, an Overhead-angle indicates a take looking down on a subject from an almost perpendicular direction.
On the other hand, we categorize camera level (i.e., the height of the camera in the scene in relation to the subject being framed) into
six different classes: Aerial, Eye, Shoulder, Hip, Knee, Ground, as shown in Figure 1 (second row). The particular class of Aerial-level
is used for shots taken from a considerable height, such as from a plane or a drone, showing a large portion of the surroundings. All
annotations were performed by a team of expert film scholars: two independent coders and a third person who made decisions in cases
of disagreement.

The dataset used for the task of automatic classification of camera angles and levels in movie frames has been collected from various
sources:

• All frames in classes Eye-, Shoulder-, and Hip-level were automatically sampled from films by various authors (e.g., Scorsese,
Bergman, etc.) of the main CineScale dataset.

• Classes that rarely appear in movies, such as Ground- or Knee- level shots were retrieved through Google’s image search, then
automatically downloaded, and finally manually filtered;

• Most Aerial-level images were extracted (at 10 second intervals) from videos taken by drones over various cities and landscapes
from freely available clips on the web;

• Images from other classes were scraped from shot examples taken from [Film School Rejects’ online database](https://shots.filmschoolrejects.com/)

<!-- #region -->
<section class="showcase">
    <div class="showcase-content">
    <h4 id="get-the-data">Get the data</h4>

Please read the Research Use Agreement provided below. 
        
<pre class="highlight" style="white-space: pre-wrap">
<b>Dataset Research Use Agreement</b>

<div style="text-align: left">
<b>Premise</b>: this project involves a set of activities aiming at AI-driven interpretation of cinematic data. The research activities are conducted by the Department of Information  Engineering (DII) of the University of Brescia, Brescia, Italy (UniBS).
The dataset is a collection of images and related data and metadata that is made accessible for Research use only, starting from this website and after acceptance of the following terms of use. 

<b>By registering for downloads, you are agreeing to this:</b>

1.	Permission is granted to view and use the Dataset without charge for research purposes only. Its sale is prohibited. Any non-academic research use need to be evaluated case by case by the DII. If you intend to use this Dataset for any non-academic research use, you need to communicate it describing the intended use and receive approval by the DII.
2.	In agreement with the mission of UniBS to promote the publication of scientific knowledge as open data, any computational model or algorithm that have used the Dataset and is publicly referenced (e.g. in a publication etc..) is suggested to be shared including the code and model weights and any case will give appropriate credit by correctly citing the AniFeature project scientific papers, but not in any way that suggests that UniBS endorses you or your use.
3.	Other than the rights granted herein, UNIBS retains all rights, title, and interest in the Dataset.
4.	You may make a verbatim copy of the "AniFeature Dataset" for uses as permitted in this Research Use Agreement. If another user within your organization wishes to use the Dataset, they must comply with all the terms of this Research Use Agreement.
5.	YOU MAY NOT DISTRIBUTE, PUBLISH, OR REPRODUCE A COPY of any portion or all of the Dataset to others without specific prior written permission from the DII.
6.	You must not modify, reverse engineer, decompile, or create derivative works from the Dataset. You must not remove or alter any copyright or other proprietary notices in the Dataset.
7.	THE Dataset IS PROVIDED «AS IS,» AND UNIBS AND ELTE DO NOT MAKE ANY WARRANTY, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE, NOR DO THEY ASSUME ANY LIABILITY OR RESPONSIBILITY FOR THE USE OF THIS Dataset.
8.	Any violation of this Research Use Agreement or other impermissible use shall be grounds for immediate termination of use of this Dataset. In the event that UniBS determines that the recipient has violated this Research Use Agreement or other impermissible use has been made, they may direct that the undersigned data recipient immediately return all copies of the Dataset and retain no copies thereof even if you did not cause the violation or impermissible use.
9.	You agree to indemnify and hold UniBS harmless from any claims, losses or damages, including legal fees, arising out of or resulting from your use of the Dataset or your violation or role in violation of these Terms. You agree to fully cooperate in UniBS defense against any such claims.
</div>

</pre>
</div>

<p><centered>
<a href="https://data.mendeley.com/datasets/h4n3gn93gz" class="button is-success is-medium">Download</a>
</centered></p>
<br />
</section>

## Results

<div class="columns is-mobile is-centered is-vcentered">
  <div class="column is-4">
      Camera Angle<br/>
      <img src="/img/cm_angle.png">
  </div>
  <div class="column is-4">
      Camera Level<br/>
      <img src="/img/cm_level.png">
  </div>
</div>

The matrices in the Figures represent the results obtained with the models trained with the training datasets and evaluated with the test datasets. The following F1-scores emerge from the results:
<table>
      <thead>
        <tr>
          <th>Camera features</th>
          <th>F1-macro</th>
          <th>F1-weighted</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Camera Angle</td>
          <td>0.94</td>
          <td>0.96</td>
        </tr>
        <tr>
          <td>Camera Level</td>
          <td>0.91</td>
          <td>0.95</td>
        </tr>
      </tbody>    
    </table>


## Get the demo and the model

<div class="columns is-mobile is-centered is-vcentered">
  <div class="column">
    <span>
        Hereafter, you can find a convenient jupyter notebook with a demo. Updated versions of the model are also provided.<br /><br />
        <a href="https://colab.research.google.com/github/CineScale/CineScale.github.io/blob/master/model/predict_camera_angle_level.ipynb" class="button is-primary is-outlined is-medium">Jupyter notebook</a>
        <a href="https://drive.google.com/file/d/1opv8MpHvrCdNInZQmnVklkA8Vxu6tFHT/view?usp=sharing" class="button is-info is-outlined is-medium">Camera Level&Angle - Pytorch Model</a>
    </span>
  </div>
</div>


## Citations

For any use or reference to this project please cite the following papers.

```
@INPROCEEDINGS{camera_level_angle23,
AUTHOR = {Savardi Mattia and  András B. {Kovács}  and Signoroni Alberto and Benini Sergio},
TITLE = {Recognition of Camera Angle and Camera Level in Movies from Single Frames},
booktitle={IMX2023 Joint Workshop on "Intelligent Cinematography and Editing" and "Emotions in Movies"},
year={2023},
organization={}
}
  
```
