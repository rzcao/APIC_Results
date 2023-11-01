---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: APIC results
---


<style>
  
    .container {
        position: relative;
    }
    .resizer {
        background: #fff2d183;
        cursor: ew-resize;
        height: 100%;
        left: 50%;
        position: absolute;
        top: 0;
        width: 8px;
        @media (max-width: 600px){
            width: 12px;
        }
        @media (max-width: 800px){
            width: 10px;
        }
    }
    .modified-image {
        background-position: top left;
        background-repeat: no-repeat;
        background-size: auto 100%;
        height: 100%;
        left: 0;
        position: absolute;
        top: 0;
        width: 50%;
    }
    .container before {
      position: absolute;
      left: 10px;
      top: 5px;
    }
    .container after {
      position: absolute;
      right: 10px;
      top: 5px;
    }
    .container beforeNew {
      position: absolute;
      left: 15px;
      top: 10px;
    }
    .container afterNew {
      position: absolute;
      right: 12%;
      top: 10px;
    }
    .container afterNewPhase {
      position: absolute;
      right: 15%;
      top: 10px;
    }
          
</style>

<style>
* {
  box-sizing: border-box;
}

.column {
  float: left;
  width: 50%;
  padding: 5px;
}

/* Clearfix (clear floats) */
.row::after {
  content: "";
  clear: both;
  display: table;
}

.div{
float: left;
width: 300px;
}
</style>

## Reconstruction using a small dataset
We imaged a Siemens star target and conducted reconstructions using FPM and APIC with a small dataset. We also imaged the Siemens star target using a 40x objective, whose NA is matched with the theoretical synthetic NA of APIC. The results are shown in the following. Although FPM's reconstruction is visually similar to the other two images, we can nonetheless see that the reconstructed spokes in FPM are distorted (see the spokes on the upper half of the image). From the figure on the right, we can see APIC is closer to the ground truth.
<div class="row">
  <div class="column">
    <div class="container">
      <div class="modified-image" style="background-image: url('img/Siemens_smallDataset_FPM.jpg')"></div>
      <div class="resizer" id="dragMe1"></div>
      <img src="img/Siemens_smallDataset_APIC.jpg">
      <beforeNew><h2 style="color:floralwhite;">FPM</h2></beforeNew>
      <afterNewPhase><h2 style="color:floralwhite;">APIC</h2></afterNewPhase>
    </div>
    <figcaption>Fig. 1. Reconstructed Siemens star target using FPM and APIC.</figcaption>
  </div>
  <div class="column">
    <div class="container">
      <div class="modified-image" style="background-image: url('img/Siemens_smallDataset_GT.jpg')"></div>
      <div class="resizer" id="dragMe2"></div>
      <img src="img/Siemens_smallDataset_APIC.jpg">
      <beforeNew><h2 style="color:floralwhite;">GT</h2></beforeNew>
      <afterNewPhase><h2 style="color:floralwhite;">APIC</h2></afterNewPhase>
    </div>
    <figcaption>Fig. 2. Reconstruction of APIC vs the ground truth.</figcaption>
  </div>
</div>
<div style="line-height:150%;">
    <br>
</div>

## Highly aberrated samples

The following shows an example of using APIC to extract aberration of an imaging system and perform complex field reconstruction with aberration correction. FPM reconstructed amplitude and phase are also shown for comparison.

<div class="row">
  <div class="column">
    <div class="container">
      <div class="modified-image" style="background-image: url('img/Thyroid_amp_FPM.jpg')"></div>
      <div class="resizer" id="dragMe3"></div>
      <img src="img/Thyroid_amp_APIC.jpg">
      <beforeNew><h2 style="color:black;">&nbsp;FPM</h2></beforeNew>
      <afterNew><h2 style="color:black;">APIC</h2></afterNew>
    </div>
    <figcaption>Fig. 3. Amplitude reconstructions of FPM and APIC.</figcaption>
  </div>
  <div class="column">
    <div class="container">
      <div class="modified-image" style="background-image: url('img/Thyroid_phase_FPM_pi_2.jpg')"></div>
      <div class="resizer" id="dragMe4"></div>
      <img src="img/Thyroid_phase_APIC_pi_2.jpg">
      <beforeNew><h2 style="color:black;">FPM</h2></beforeNew>
      <afterNewPhase><h2 style="color:black;">APIC</h2></afterNewPhase>
    </div>
    <figcaption>Fig. 4. Phase reconstructions of FPM and APIC.</figcaption>
  </div>
</div>
<div style="line-height:50%;">
    <br>
</div>

As we can see from the results shown above, APIC successfully reconstructed the phase and amplitude of the sample. In contrast, FPM reconstructions are severely distorted. This is because FPM failed to retrieve the correct aberration function while APIC demonstrated unparalleled robustness against aberrations.
<div style="line-height:150%;">
    <br>
</div>

## H&E stained breast cancer cells 

Here is an example of using APIC to do color reconstructions. A hematoxylin and eosin (H&E) stained breast cancer sample was imaged using red, green, and blue LEDs. APIC was used to do the complex field reconstructions. 

The comparison of a small region of APIC reconstructed result and the raw measurement under Kohler illumination can be found in the figuer below.


Click and slide the light orange slider to compare two images. (To download the full size image, click here:
<a href="img/APIC_amp_256wb.jpeg">APIC_H&E</a>, 
<a href="img/Kohler_amp_wb.jpeg">Kohler_illumination</a> )

<div class="container">
      <div class="modified-image" style="background-image: url('img/Kohler_amp_wb_crop.jpeg')"></div>
      <div class="resizer" id="dragMe5"></div>
      <img src="img/APIC_amp_256wb_crop.jpeg">
      <before><h1 style="color:floralwhite;">Kohler</h1></before>
      <after><h1 style="color:floralwhite;">APIC</h1></after>
</div>
<figcaption>Fig. 5. Color image under kohler illumination and reconstructed color image using APIC.</figcaption>
<div style="line-height:50%;">
    <br>
</div>

The comparison of FPM reconstructed color image and APIC reconstructed image can be found below. We selected two different regions to do reconstructon. The one shown on the left was reconstructed using the central patch and the one on the right was from an off-axis patch. It is easy to see the reconstruction using FPM is noisier compared with the one reconstructed by APIC.

<div class="row">
  <div class="column">
    <div class="container">
      <div class="modified-image" style="background-image: url('img/FPM_RGB_compare_central.jpg')"></div>
      <div class="resizer" id="dragMe6"></div>
      <img src="img/APIC_RGB_compare_central.jpg">
      <before><h2 style="color:floralwhite;">FPM</h2></before>
      <after><h2 style="color:floralwhite;">APIC</h2></after>
    </div>
    <figcaption>Fig. 6. FPM and APIC reconstructed color image (central patch).</figcaption>
  </div>
  <div class="column">
    <div class="container">
      <div class="modified-image" style="background-image: url('img/FPM_RGB_compare.jpg')"></div>
      <div class="resizer" id="dragMe7"></div>
      <img src="img/APIC_RGB_compare.jpg">
      <before><h2 style="color:floralwhite;">FPM</h2></before>
      <after><h2 style="color:floralwhite;">APIC</h2></after>
    </div>
    <figcaption>Fig. 7. FPM and APIC reconstructed color image (offaxis patch).</figcaption>
  </div>
</div>


<script>
      document.addEventListener('DOMContentLoaded', function () {
        // Query the element
        var i ;
        currentResizer = document.getElementsByClassName("resizer")
        
        for (i = 0; i < currentResizer.length; i++){
            compareIm(currentResizer[i])
        }
      
        function compareIm(resizer) {
        const leftSide = resizer.previousElementSibling;
        const rightSide = resizer.nextElementSibling;
  
        // The current position of mouse
        let x = 0;
        let y = 0;
        let leftWidth = 0;
  
        // Handle the mousedown event
        // that's triggered when user drags the resizer
        const mouseDownHandler = function (e) {
            // Get the current mouse position
            x = e.clientX;
            y = e.clientY;
            leftWidth = leftSide.getBoundingClientRect().width;
  
            // Attach the listeners to `document`
            document.addEventListener('mousemove', mouseMoveHandler);
            document.addEventListener('mouseup', mouseUpHandler);
        };

        const touchStartHandler = function (e) {
            // Get the current touch position
            x = e.touches[0].clientX;
            y = e.touches[0].clientY;
            leftWidth = leftSide.getBoundingClientRect().width;
  
            // Attach the listeners to `document`
            document.addEventListener('touchmove', touchMoveHandler);
            document.addEventListener('touchend', touchEndHandler);
        };
  
        const mouseMoveHandler = function (e) {
            // How far the mouse has been moved
            const dx = e.clientX - x;
            const dy = e.clientY - y;
  
            let newLeftWidth = ((leftWidth + dx) * 100) / resizer.parentNode.getBoundingClientRect().width;
            newLeftWidth = Math.max(newLeftWidth, 0);
            newLeftWidth = Math.min(newLeftWidth, 100);
  
            leftSide.style.width = `${newLeftWidth}%`;
            resizer.style.left = `${newLeftWidth}%`;
  
            resizer.style.cursor = 'col-resize';
            resizer.parentNode.style.cursor = 'col-resize';
  
            leftSide.style.userSelect = 'none';
            leftSide.style.pointerEvents = 'none';
  
            rightSide.style.userSelect = 'none';
            rightSide.style.pointerEvents = 'none';
        };

        const touchMoveHandler = function (e) {
            // How far the mouse has been moved
            const dx = e.changedTouches[0].clientX - x;
            const dy = e.changedTouches[0].clientY - y;
  
            let newLeftWidth = ((leftWidth + dx) * 100) / resizer.parentNode.getBoundingClientRect().width;
            newLeftWidth = Math.max(newLeftWidth, 0);
            newLeftWidth = Math.min(newLeftWidth, 100);
  
            leftSide.style.width = `${newLeftWidth}%`;
            resizer.style.left = `${newLeftWidth}%`;
  
            resizer.style.cursor = 'col-resize';
            resizer.parentNode.style.cursor = 'col-resize';
  
            leftSide.style.userSelect = 'none';
            leftSide.style.pointerEvents = 'none';
  
            rightSide.style.userSelect = 'none';
            rightSide.style.pointerEvents = 'none';
        };
  
        const mouseUpHandler = function () {
            resizer.style.removeProperty('cursor');
            resizer.parentNode.style.removeProperty('cursor');
  
            leftSide.style.removeProperty('user-select');
            leftSide.style.removeProperty('pointer-events');
  
            rightSide.style.removeProperty('user-select');
            rightSide.style.removeProperty('pointer-events');
  
            // Remove the handlers of `mousemove` and `mouseup`
            document.removeEventListener('mousemove', mouseMoveHandler);
            document.removeEventListener('mouseup', mouseUpHandler);
        };

        const touchEndHandler = function () {
            resizer.style.removeProperty('cursor');
            resizer.parentNode.style.removeProperty('cursor');
  
            leftSide.style.removeProperty('user-select');
            leftSide.style.removeProperty('pointer-events');
  
            rightSide.style.removeProperty('user-select');
            rightSide.style.removeProperty('pointer-events');
  
            // Remove the handlers of `touchmove` and `touchend`
            document.removeEventListener('touchmove', touchMoveHandler);
            document.removeEventListener('touchend', touchEndHandler);
        };
  
        // Attach the handler
        resizer.addEventListener('mousedown', mouseDownHandler);
        resizer.addEventListener('touchstart', touchStartHandler);
    }});
</script>

