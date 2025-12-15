// add dual colour in css use this 
.sidebar {
    width: 60px; /* Collapsed width */
    background: linear-gradient(135deg, #1E343D, #A7C3CD); // this is dual  colour
    color: white;
    padding: 20px 10px;
    height: 100vh;
    position: fixed;
    left: 0;
    top: 0;
    transition: width 0.3s ease-in-out;
    text-align: center;
    overflow: hidden;
    white-space: nowrap;
}

/// Create a search bar like a google ///
js and html code to search courses on page on basis of user input

<div class="search-bar">
        <input type="text" id="search-input" placeholder="Search Course">
    <i class="fas fa-search search-icon"></i>
</div>

// // Search Functionality javascript code //
document.addEventListener("DOMContentLoaded", () => {
    const searchInput = document.getElementById("search-input");
    const searchIcon = document.querySelector(".search-icon");
    const courseCards = document.querySelectorAll(".event-card");

    function filterCourses() {
        const searchText = searchInput.value.toLowerCase().trim();

        courseCards.forEach(card => {
            const courseTitle = card.querySelector("h3").textContent.toLowerCase();
            card.style.display = searchText === "" || courseTitle.includes(searchText) ? "block" : "none";
        });
    }

    // Trigger search on search icon click
    searchIcon.addEventListener("click", filterCourses);

    // Trigger search on Enter key press inside the search input
    searchInput.addEventListener("keypress", (event) => {
        if (event.key === "Enter") {
            filterCourses();
        }
    });

    // Reset filter when the input is cleared
    searchInput.addEventListener("input", () => {
        if (searchInput.value.trim() === "") {
            filterCourses();
        }
    });
});
