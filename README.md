# Preloader

Simple preloader in JS, HTML and CSS for site.

#### HTML
    
```html
<div class="preloader">
    <div class="loader"><img src="/media/swallow-emb.svg" alt=""></
</div>
```

#### CSS
    
```CSS
.preloader {
    background: black;
    position: fixed;
    height: 100%;
    width: 100%;
    left: 0px;
    top: 0px;
    z-index: 2;
    transition: 1s all;
    opacity: 1;
    visibility: visible;
}

.preloader .loader {
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    width: 15%;
    height: auto;
    animation: opacity 3s ease-in 0s infinite alternate-reverse;
}

.done {
    opacity: 0;
    visibility: hidden;
}

@keyframes opacity {
    from {
        opacity: 100%;
    }
    to {
        opacity: 10%;
    }
}
```

#### JavaScript
    
```JavaScript
document.body.onload = function() {
    setTimeout(function() {
        var preloader = document.querySelector(".preloader");
        console.log(preloader);
        if (!preloader.classList.contains('done')) {
            preloader.classList.add('done');
        };
    }, 1000);
}
```