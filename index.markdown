---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: APIC results
---

## H&E stained breast cancer cells 

Here is an example of using APIC to do color reconstructions. A hematoxylin and eosin (H&E) stained breast cancer sample was imaged under red, green, and blue LEDs. APIC was used to do the complex field reconstructions. 

The comparison of a small region of APIC reconstructed result and the raw measurement under Kohler illumination can be found in the figuer below.


Click and slide the light orange slider to compare two images. (To download the full size image, click here:
<a href="img/APIC_amp_256wb.jpeg">APIC_H&E</a>, 
<a href="img/Kohler_amp_wb.jpeg">Kohler_illumination</a> )

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
            width: 16px;
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
          
</style>
  
  
<div class="container">
      <div class="modified-image" style="background-image: url('img/Kohler_amp_wb_crop.jpeg')"></div>
      <div class="resizer" id="dragMe"></div>
      <img src="img/APIC_amp_256wb_crop.jpeg">
      <before><h1 style="color:floralwhite;">Kohler</h1></before>
      <after><h1 style="color:floralwhite;">APIC</h1></after>
</div>
<script>
      document.addEventListener('DOMContentLoaded', function () {
        // Query the element
        const resizer = document.getElementById('dragMe');
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
    });
</script>

## Highly aberrated samples

The following shows an example of using APIC to extract aberration of an imaging system and perform complex field reconstruction with aberration correction.