<h1 align="center">👋 <span id="typewriter"></span></h1>

<script>
    const texts = [
        "Hi, I'm Raiya Yusuf Priatmojo",
        "Mechatronics Engineering Student", 
        "at Yogyakarta State University"
    ];
    
    let textIndex = 0;
    let charIndex = 0;
    let currentText = '';
    let isDeleting = false;
    let typeSpeed = 100;

    function typeWriter() {
        const typewriterElement = document.getElementById('typewriter');
        
        if (textIndex === texts.length) {
            textIndex = 0;
        }
        
        currentText = texts[textIndex];
        
        if (isDeleting) {
            typewriterElement.textContent = currentText.substring(0, charIndex - 1);
            charIndex--;
            typeSpeed = 50;
        } else {
            typewriterElement.textContent = currentText.substring(0, charIndex + 1);
            charIndex++;
            typeSpeed = 100;
        }
        
        if (!isDeleting && charIndex === currentText.length) {
            typeSpeed = 2000;
            isDeleting = true;
        } else if (isDeleting && charIndex === 0) {
            isDeleting = false;
            textIndex++;
            typeSpeed = 500;
        }
        
        setTimeout(typeWriter, typeSpeed);
    }

    document.addEventListener('DOMContentLoaded', function() {
        setTimeout(typeWriter, 1000);
    });
</script>

<style>
    #typewriter {
        border-right: 3px solid #3B82F6;
        padding-right: 5px;
        animation: blink 0.7s infinite;
    }

    @keyframes blink {
        0%, 100% { border-color: transparent; }
        50% { border-color: #3B82F6; }
    }
</style>

<img src="https://raw.githubusercontent.com/raiyayusuf/raiyayusuf/output/snake.svg" alt="Snake animation" />

###
