// how to create multi-select optionset on power portal page
<div>
    <div class="custom-multiselect">
        <button class="multi-select-btn">Select Categories </button>
        <div class="multi-select-dropdown">
            <label><input type="checkbox" value="Data Analysis"> Data Analysis</label>
            <label><input type="checkbox" value="Power Platform"> Power Platform</label>
            <label><input type="checkbox" value="Power Platform"> Microsoft</label>
          </div>
</div>


// javascript code //
 document.querySelector(".multi-select-btn").addEventListener("click", function () {
      document.querySelector(".custom-multiselect").classList.toggle("active");
  });

  document.addEventListener("click", function (event) {
      let dropdown = document.querySelector(".custom-multiselect");
      if (!dropdown.contains(event.target)) {
          dropdown.classList.remove("active");
      }
  });