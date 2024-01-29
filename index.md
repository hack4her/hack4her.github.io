---
layout: default
title: Hack4Her, empowering tech brilliance
description: Hack4Her is a female-focused Hackathon in the Netherlands.
---

# What is Hack4Her?
Hack4Her is the _**only female-focused**_ student hackathon in the Netherlands in the past 5 years. ...

<div style="display: flex; flex-wrap: wrap;">
    <img src="_MG_1646.JPG" alt="Image 1" width="300" style="margin-right: 20px;"/>
    <img src="_MG_1655.JPG" alt="Image 2" width="300" style="margin-right: 20px;"/>
    <img src="_MG_1708.JPG" alt="Image 4" width="300" style="margin-right: 20px;"/>
    <img src="_MG_1712.JPG" alt="Image 5" width="300" style="margin-right: 20px;"/>
    <img src="_MG_1715.JPG" alt="Image 6" width="300" style="margin-right: 20px;"/>
    <img src="_MG_1731.JPG" alt="Image 7" width="300" style="margin-right: 20px;"/>
    <img src="_MG_1733.JPG" alt="Image 8" width="300" style="margin-right: 20px;"/>
</div>

<script>
document.addEventListener('DOMContentLoaded', function () {
    function moveImages() {
        const images = document.querySelectorAll('.dynamic-image');
        images.forEach(img => {
            const x = Math.random() * (window.innerWidth - img.clientWidth);
            const y = Math.random() * (window.innerHeight - img.clientHeight);

            img.style.position = 'absolute';
            img.style.left = `${x}px`;
            img.style.top = `${y}px`;
        });
    }

    setInterval(moveImages, 2000);
    moveImages();
});
</script>
# We look forward to Hack4Her 2024, bigger, better, with students from all over Netherlands welcome!
