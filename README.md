<script>
    //Fading Fixed Menu, modified from Fixed Menu v1.3.1

    //Replace ID below with your own box ID
    var boxToAppend = '#lp-pom-box-235';
    //Choose pixel height of when menu fades in. Use the height of a page section like this: $("#lp-pom-block-93").height();
    var showHeight = 300;

    //Set to 'header' or 'footer'
    var headerOrFooter = 'header';

    var backgroundCSS = {
        "position": "fixed",
        "left": "0",
        "top": "0px",
        "bottom": "auto",
        "width": "100%",
        "z-index": "899",
        "box-shadow": "5px 5px 15px 0 rgba(31, 31, 31, 0.07)"
    };
    var colorOverlayCSS = {
        "position": "fixed",
        "left": "0",
        "top": "0px",
        "bottom": "auto",
        "width": "100%",
        "z-index": "auto",
        "border-style": "none none none none"
    };
    var childrenCSS = {
        "position": "fixed",
        "left": "auto",
        "top": "0px",
        "bottom": "auto",
        "width": "100%",
        "z-index": "999",
        "border-style": "none none none none",
        "border-width": "0px",
        "background": "none"
    };

    if (headerOrFooter === 'footer') {
        backgroundCSS["top"] = 'auto';
        backgroundCSS["bottom"] = '0px';
        colorOverlayCSS["top"] = 'auto';
        colorOverlayCSS["bottom"] = '0px';
        childrenCSS["top"] = 'auto';
        childrenCSS["bottom"] = '0px';
    }

    var boxParent = $(boxToAppend).parent();
    var boxClone = $(boxToAppend).clone()

    boxClone.appendTo(boxParent).css(backgroundCSS).children().remove();
    $(boxToAppend).css(childrenCSS);
    $(boxToAppend + '-color-overlay').appendTo(boxClone).css(colorOverlayCSS);


    var bothBoxes = boxToAppend + ', ' + boxToAppend + '-color-overlay';
    $(window).scroll(function() {
        if ($(this).scrollTop() > showHeight) {
            $(bothBoxes).fadeIn();
        } else {
            $(bothBoxes).fadeOut();
        }
    });

</script>
