---
title: "#CineScale: Recognising Shot Scale with AI"
subtitle: Shot Scale Project and Database
layout: page
show_sidebar: false
hero_image: /img/header.png
---

<!-- #region -->
# Shot Scale Recognition


## What is the aim?
<div class="columns is-mobile is-centered is-vcentered">
  <div class="column is-4">
    <span>The apparent distance of the camera from the subject of a filmed scene, namely <b>shot scale</b>, is one of the prominent formal features of any filmic product. <br/>
        We propose to use Convolutional Neural Networks for the automatic classification of shot scale for investigating the relationship between shot scale computed of large movie corpora and the viewers’ emotional involvement. To demonstrate the utility of shot scale, we show how to perform automatic attribution of movie’s authorship by the statistical analysis of shot scale, when combined with shot duration. Then, we measure how shot scale affects both lower and higher complexity responses in viewers, relating shot scales to viewers’ rating on film mood and narrative engagement.
      </span>
  </div>
  <div class="column">
    <img src="/img/shottype.jpg">
  </div>
</div>

[Paper on shot scale recognition](https://ieeexplore.ieee.org/document/8451474){: .button}
[Paper on movie’s authorship](https://ieeexplore.ieee.org/document/8826335){: .button}
[Paper on film mood, and narrative engagement](https://ieeexplore.ieee.org/document/8822965){: .button}



<!-- #endregion -->

## Dataset

<!-- #region -->
We collect a large dataset of shot frames (<b>792K</b>, with an average of 6389 frames) from the full filmographies by six different authors (Scorsese, Godard, Tarr, Fellini, Antonioni, and Bergman) for a total number of 124 movies. Each frame, extracted at 1 frame per second, is annotated with its shot scale using the following categories: Extreme Close Up (ECU), Close Up (CU), Medium Close Up (MCU), Medium Shot (MS), Medium Long Shot (MLS), Long Shot (LS), Extreme Long Shot (ELS), Foreground Shot (FS), and Insert Shots (IS).

Two independent coders code the 124 movies and a third person checks their coding and makes decisions in cases of disagreement. The inter-rater reliability of ratings is computed, obtaining a Fleiss’ Kappa index of agreement between the annotations of 0.64, which indicates sufficient inter-rater agreement (95% confidence interval: 0.635-0.643).

*Below a list of each field in the* **annotation** file (`{$year}_{$director}_-_{$title}.csv`), *with explanations where relevant*
<details>
 <summary>Scheme (click to open)</summary>
    <table>
  <thead>
    <tr>
      <th>Attribute</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>time</td>
      <td>Time from the movie beginning</td>
    </tr>
    <tr>
      <td>shotscale</td>
      <td>Shot scale class, see next table </td>
    </tr>
  </tbody>    
    </table>
​    

 <table>
  <thead>
    <tr>
      <th>Code</th>
      <th>Abbreviation</th>
      <th>Class</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>FS</td>
      <td>Foreground Shot</td>
    </tr>
    <tr>
      <td>1</td>
      <td>ECU</td>
      <td>Extreme Close Up</td>
    </tr>
    <tr>
      <td>2</td>
      <td>CU</td>
      <td>Close Up</td>
    </tr>
    <tr>
      <td>3</td>
      <td>MCU</td>
      <td>Medium Close Up</td>
    </tr>
    <tr>
      <td>4</td>
      <td>MS</td>
      <td>Medium Shot</td>
    </tr>
    <tr>
      <td>5</td>
      <td>MLS</td>
      <td>Medium Long Shot</td>
    </tr>
    <tr>
      <td>6</td>
      <td>LS</td>
      <td>Long Shot</td>
    </tr>
    <tr>
      <td>7</td>
      <td>ELS</td>
      <td>Extreme Long Shot</td>
    </tr>
    <tr>
      <td>8</td>
      <td>IS</td>
      <td>Insert Shots</td>
    </tr>
    <tr>
      <td>9</td>
      <td>NA</td>
      <td>Not available</td>
    </tr>
  </tbody>    
 </table>
</details>
<br />
<!-- #endregion -->

<!-- #region -->
<section class="showcase">
    <div class="showcase-content">
    <h4 id="get-the-data">Get the data</h4>

Please read the Research Use Agreement provided below. Once you register to download the CineScale Dataset, you will receive a link to the download over email. 
        
It is forbidden to share the link to download the dataset with others.

<pre class="highlight" style="white-space: pre-wrap">
<b>"CineScale Dataset" Research Use Agreement</b>

<div style="text-align: left">
<b>Premise</b>: the CineScale project involves a set of activities aiming at AI-driven interpretation of cinematic data. The research activities are conducted by a joint project team (JPT) belonging to the Department of Information  Engineering (DII) of the University of Brescia, Brescia, Italy (UniBS) and ELTE department of Art Theory and Communication, Bupapest, Hungary (ELTE).
The "CineScale Dataset" is a collection of images and related data and metadata that is made accessible for Research use only, starting from this website and after acceptance of the following terms of use. 

<b>By registering for downloads, you are agreeing to this:</b>

1.	Permission is granted to view and use the "CineScale Dataset" without charge for research purposes only. Its sale is prohibited. Any non-academic research use need to be evaluated case by case by the JPT. If you intend to use this dataset for any non-academic research use, you need to communicate it describing the intended use and receive approval by the JPT.
2.	In agreement with the mission of UniBS and ELTE to promote the publication of scientific knowledge as open data, any computational model or algorithm that have used the "CineScale Dataset" and is publicly referenced (e.g. in a publication etc..) is suggested to be shared including the code and model weights and any case will give appropriate credit by correctly citing the CineScale project scientific papers, but not in any way that suggests that ELTE and/or UniBS endorses you or your use.
3.	Other than the rights granted herein, ELTE and UNIBS retains all rights, title, and interest in the "CineScale Dataset".
4.	You may make a verbatim copy of the "CineScale Dataset" for uses as permitted in this Research Use Agreement. If another user within your organization wishes to use the "CineScale Dataset", they must comply with all the terms of this Research Use Agreement.
5.	YOU MAY NOT DISTRIBUTE, PUBLISH, OR REPRODUCE A COPY of any portion or all of the "CineScale Dataset" to others without specific prior written permission from the JPT.
6.	You must not modify, reverse engineer, decompile, or create derivative works from the "CineScale Dataset". You must not remove or alter any copyright or other proprietary notices in the "CineScale Dataset".
7.	THE "CineScale Dataset" IS PROVIDED «AS IS,» AND UNIBS AND ELTE DO NOT MAKE ANY WARRANTY, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE, NOR DO THEY ASSUME ANY LIABILITY OR RESPONSIBILITY FOR THE USE OF THIS "CineScale Dataset".
8.	Any violation of this Research Use Agreement or other impermissible use shall be grounds for immediate termination of use of this "CineScale Dataset". In the event that ELTE or UniBS determines that the recipient has violated this Research Use Agreement or other impermissible use has been made, they may direct that the undersigned data recipient immediately return all copies of the "CineScale Dataset" and retain no copies thereof even if you did not cause the violation or impermissible use.
9.	You agree to indemnify and hold ELTE and UniBS harmless from any claims, losses or damages, including legal fees, arising out of or resulting from your use of the "CineScale Dataset" or your violation or role in violation of these Terms. You agree to fully cooperate in ELTE and UniBS defense against any such claims.
</div>

</pre>


<!-- Begin Mailchimp Signup Form -->
<link href="//cdn-images.mailchimp.com/embedcode/classic-10_7.css" rel="stylesheet" type="text/css">
<style type="text/css">
	#mc_embed_signup{background:#fff; clear:left; font:14px Helvetica,Arial,sans-serif; }
	/* Add your own Mailchimp form style overrides in your site stylesheet or in this style block.
	   We recommend moving this block and the preceding CSS link to the HEAD of your HTML file. */
</style>
<div id="mc_embed_signup">
<form action="https://gmail.us2.list-manage.com/subscribe/post?u=e48e43990a072daed947d11cf&amp;id=609f59ff7f" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
    <div id="mc_embed_signup_scroll">
	<h2>Subscribe</h2>
<div class="indicates-required"><span class="asterisk">*</span> indicates required</div>
<div class="mc-field-group">
	<label for="mce-EMAIL">Email Address  <span class="asterisk">*</span>
</label>
	<input type="email" value="" name="EMAIL" class="required email" id="mce-EMAIL">
</div>
<div class="mc-field-group">
	<label for="mce-FNAME">First Name </label>
	<input type="text" value="" name="FNAME" class="" id="mce-FNAME">
</div>
<div class="mc-field-group">
	<label for="mce-LNAME">Last Name </label>
	<input type="text" value="" name="LNAME" class="" id="mce-LNAME">
</div>
<div class="mc-field-group">
	<label for="mce-SCHOOL">School/Organization  <span class="asterisk">*</span>
</label>
	<input type="text" value="" name="SCHOOL" class="required" id="mce-SCHOOL">
</div>
<div class="mc-field-group">
	<label for="mce-ROLE">Role  <span class="asterisk">*</span>
</label>
	<input type="text" value="" name="ROLE" class="required" id="mce-ROLE">
</div>
<div class="mc-field-group input-group">
    <strong>Terms of use  <span class="asterisk">*</span>
</strong>
    <ul><li><input type="radio" value="I accept the Research User Agreement provided above" name="TERMS" id="mce-TERMS-0"><label for="mce-TERMS-0"> I accept the Research User Agreement provided above</label></li>
</ul>
</div>
	<div id="mce-responses" class="clear">
		<div class="response" id="mce-error-response" style="display:none"></div>
		<div class="response" id="mce-success-response" style="display:none"></div>
	</div>    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;" aria-hidden="true"><input type="text" name="b_e48e43990a072daed947d11cf_609f59ff7f" tabindex="-1" value=""></div>
    <div class="clear"><input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button"></div>
    </div>
</form>
</div>
<script type='text/javascript' src='//s3.amazonaws.com/downloads.mailchimp.com/js/mc-validate.js'></script><script type='text/javascript'>(function($) {window.fnames = new Array(); window.ftypes = new Array();fnames[0]='EMAIL';ftypes[0]='email';fnames[1]='FNAME';ftypes[1]='text';fnames[2]='LNAME';ftypes[2]='text';fnames[3]='SCHOOL';ftypes[3]='text';fnames[4]='ROLE';ftypes[4]='text';fnames[5]='TERMS';ftypes[5]='radio';}(jQuery));var $mcj = jQuery.noConflict(true);</script>
<!--End mc_embed_signup--></div>
</section>
<!-- #endregion -->

<!-- #region -->
## Results

VGG-16 performs best with an overall precision of 94%, recall 94%, and accuracy 94%. 
For each CNN we test and compare four different configurations: A) training from scratch, B) loading weights from ImageNet and fine-tuning the last layer only, C) fine-tuning all fully-connected layers, and D) fine-tuning the whole network. 
Classification results for all other configurations using VGG-16 follow (in terms of accuracy): configuration A, 80%; configuration B, 89%; configuration C, 90%. The contribution of the post-processing smoothing increases the accuracy score of +0.5% on average. 

<div class="columns is-mobile is-centered is-vcentered">
  <div class="column is-3">
      AlexNet<br/>
      <img src="/img/alex-4.png">
  </div>
  <div class="column is-3">
      GoogleLeNet<br/>
      <img src="/img/google-4.png">
  </div>
  <div class="column is-3">
      VGG16<br/>
      <img src="/img/vgg-4v2.png">
  </div>
</div>


### Error analysis
Left to right: a borderline case; a low contrast frame; an artistic shot; an error due to annotation (orange: GT scale; cyan: predicted scale). 
<div class="columns is-mobile is-centered is-vcentered">
  <div class="column is-6">
    <img src="/img/errors.jpg">
  </div>
</div>
<!-- #endregion -->

## Get the model

<div class="columns is-mobile is-centered is-vcentered">
  <div class="column is-5">
      <img src="/img/arch.png">
  </div>
  <div class="column">
    <span>
        Hereafter, you can find a convenient jupyter notebook with a demo. It is included an updated version of the model that makes use of <i>DenseNet</i>, improving the overall accuracy by ~3% with respect to the best model presented on the research article (VGG16, see above). <br /><br />
        <a href="examples/ShotScale-test.ipynb" class="button is-primary is-outlined is-medium">Jupyter notebook</a>
        <a href="examples/model_shotscale_967.h5" class="button is-info is-outlined is-medium">Model weights</a>
        <a href="https://colab.research.google.com/github/CineScale/CineScale.github.io/blob/master/model/Demo_ShotScale_Cinescale.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Collab" class="button is-primary is-outlined is-medium"></a>
    </span>
  </div>
</div>


## Citations

For any use or reference to this project please cite the following papers.

```
@INPROCEEDINGS{SSM18, 
  author={M. Savardi and A. Signoroni and P. Migliorati and S. Benini}, 
  booktitle={2018 25th IEEE International Conference on Image Processing (ICIP)}, 
  title={Shot Scale Analysis in Movies by Convolutional Neural Networks}, 
  year={2018}, 
  pages={2620-2624}, 
  doi={10.1109/ICIP.2018.8451474}, 
  ISSN={2381-8549}, 
  month={Oct},
}

@ARTICLE{SSS19,
  author={M. {Svanera} and M. {Savardi} and A. {Signoroni} and A. B. {Kovács} and S. {Benini}},
  journal={IEEE MultiMedia}, 
  title={Who is the Film's Director? Authorship Recognition Based on Shot Features}, 
  year={2019},
  volume={26},
  number={4},
  pages={43-54},
  doi={10.1109/MMUL.2019.2940004}
}

@ARTICLE{BSB19,
  author={S. {Benini} and M. {Savardi} and K. {Bálint} and A. B. {Kovács} and A. {Signoroni}},
  journal={IEEE Transactions on Affective Computing}, 
  title={On the influence of shot scale on film mood and narrative engagement in film viewers}, 
  year={2019},
  pages={1-1},
  doi={10.1109/TAFFC.2019.2939251}
}
  
```
