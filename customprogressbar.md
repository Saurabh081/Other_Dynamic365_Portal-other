Custom Progress bar for power pages portal
    This is the id of default progress bar id == #WebFormControl_3033751c2b9c49ceb4e900510f86f0c8_ProgressIndicator
css value of the progress bar ==   in-progresss

-------------------------------------------------------------------------------------------------------------------------
## HTML CODE

<div class="wizard-progress">
  <div class="step">
    Sourcing
    <div class="node"></div>
  </div>
  <div class="step">
    Grading
    <div class="node"></div>
  </div>
  <div class="step">
    Treatment
    <div class="node"></div>
  </div>
  <div class="step">
    Attributes
    <div class="node"></div>
  </div>
  <div class="step">
    Summary
    <div class="node"></div>
  </div>
</div>

-------------------------------------------------------------------------------------------------------------------------
## CSS CODE

.wizard-progress {
    display: table;
    width: 100%;
    table-layout: fixed;
    position: relative;
    margin-top: 50px; /* Moves the custom progress bar downward */
}
.wizard-progress .step {
    display: table-cell;
    text-align: center;
    vertical-align: top;
    overflow: visible;
    position: relative;
    font-size: 14px;
    color: #000;
    font-weight: bold;
}
.wizard-progress .step:not(:last-child):before {
    content: '';
    display: block;
    position: absolute;
    left: 49%;
    top: 35px;
    background-color: #000;
    height: 8px;
    width: 100%;
}
.wizard-progress .step .node {
    display: inline-block;
    border: 6px solid #000;
    background-color: #FFF;
    border-radius: 18px;
    height: 30px;
    width: 30px;
    position: absolute;
    top: 25px;
    left: 50%;
    margin-left: -18px;
}
.wizard-progress .step.complete:before {
    background-color: #07c;
}
.wizard-progress .step.complete .node {
    border-color: #07c;
    background-color: #07c;
}
.wizard-progress .step.complete .node:before {
    font-family: FontAwesome;
    content: "\f00c";
}
.wizard-progress .step.in-progress:before {
    background: #07c;
    background: -moz-linear-gradient(left, #07c 0%, #000 100%);
    background: -webkit-linear-gradient(left, #07c 0%, #000 100%);
    background: linear-gradient(to right, #07c 0%, #000 100%);
    filter: progid:DXImageTransform.Microsoft.gradient(startColorstr="#07c", endColorstr="#fff",GradientType=1);
}
.wizard-progress .step.in-progress .node {
    border-color: #07c;
}

#WebFormControl_3033751c2b9c49ceb4e900510f86f0c8_ProgressIndicator{
    visibility: hidden !important;
}

-------------------------------------------------------------------------------------------------------------------------
## JAVASCRIPT CODE

var firstSpanValue = $('#WebFormControl_3033751c2b9c49ceb4e900510f86f0c8_ProgressIndicator')
    .children('span:first')
    .text();

// Check if the success message is displayed
if ($('#MessageLabel').text() === 'Submission completed successfully.') {
    // Hide the entire progress bar if the message appears
    $('.wizard-progress').hide();
}

$('.wizard-progress .step').each(function (index) {
    console.log("INDEX", index);
    if (index + 1 < firstSpanValue) {
        // Steps before the current step
        $(this).addClass('complete');
        $(this).removeClass('in-progress');
    } else if (index + 1 === firstSpanValue) {
        // Current step
        $(this).addClass('in-progress');
    }
});

