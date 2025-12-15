// HTML Code //
//date picker format from dd/mm/yyyy to mm/dd/yyyy in power portal page.
<div>
<label for="start-date">Start Date:</label>
        <input type="text" id="start-date" />  
        
        <label for="end-date">End Date:</label>
        <input type="text" id="end-date" placeholder="End Date"/> 
</div>


// javascript// 
$(document).ready(function () {
   
    $("#start-date, #end-date").datepicker({
        dateFormat: "mm-dd-yy", 
        changeMonth: true,
        changeYear: true
    });

/////////////////////////////////////////////////////////////////////////////////////////////////////////////
 // how to show course cards based on the start and end dates in power portal page beloew is the code.

     
    function filterCourses() {
        let startDateInput = $("#start-date").val();
        let endDateInput = $("#end-date").val();

        
        if (!startDateInput || !endDateInput) {
            $(".event-card").show();
            return;
        }

      
        let startDateFilter = new Date(startDateInput);
        let endDateFilter = new Date(endDateInput);

        $(".event-card").each(function () {
            let courseStartDateText = $(this).find("p strong:first").text().replace("From: ", "").trim();
            let courseEndDateText = $(this).find("p strong:nth-of-type(2)").text().replace("To: ", "").trim();

            let courseStartDate = new Date(courseStartDateText);
            let courseEndDate = new Date(courseEndDateText);

            
            let showCard = courseStartDate >= startDateFilter && courseEndDate <= endDateFilter;

            $(this).toggle(showCard);
        });
    }

    
    $("#start-date, #end-date").on("change", filterCourses);
});


//////////////////Normal date format //////////////
// check date format before applying on portal
<div>
        <label for="start-date">Start Date:</label>
        <input type="date" id="start-date" placeholder="Start Date"/>  
</div>