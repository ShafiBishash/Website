// Quran Explained

console.log("Quran Explained Loaded");

// Smooth scroll

document.querySelectorAll('a[href^="#"]').forEach(anchor => {

    anchor.addEventListener("click", function(e){

        e.preventDefault();

        const target = document.querySelector(this.getAttribute("href"));

        if(target){

            target.scrollIntoView({

                behavior:"smooth"

            });

        }

    });

});

// Simple fade-in animation

const observer = new IntersectionObserver(entries=>{

    entries.forEach(entry=>{

        if(entry.isIntersecting){

            entry.target.style.opacity="1";

            entry.target.style.transform="translateY(0)";

        }

    });

});

document.querySelectorAll(".card,.featured-card,.about").forEach(el=>{

    el.style.opacity="0";

    el.style.transform="translateY(25px)";

    el.style.transition=".7s";

    observer.observe(el);

});