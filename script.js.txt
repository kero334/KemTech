// JavaScript for image slider
function showImage(slider, index) {
    const images = slider.querySelectorAll('img');
    images.forEach((img, i) => {
        img.classList.toggle('active', i === index);
    });
}

function prevImage(button) {
    const slider = button.parentElement.parentElement;
    const images = slider.querySelectorAll('img');
    let currentIndex = Array.from(images).findIndex(img => img.classList.contains('active'));
    let prevIndex = (currentIndex - 1 + images.length) % images.length;
    showImage(slider, prevIndex);
}

function nextImage(button) {
    const slider = button.parentElement.parentElement;
    const images = slider.querySelectorAll('img');
    let currentIndex = Array.from(images).findIndex(img => img.classList.contains('active'));
    let nextIndex = (currentIndex + 1) % images.length;
    showImage(slider, nextIndex);
}
