//   all ------------------
function initNastik() {
    jQuery(window).on("load", function () {
        firstLoad();
    });
    function firstLoad() {
        TweenMax.to(jQuery(".loader-inner"), 1.0, {
            force3D: true,
            y: "-150px",
            opacity: 0,
            ease: Expo.easeInOut,
            onComplete: function () {
                TweenMax.to(jQuery(".loader-bg"), 0.8, {
                    force3D: true,
                    bottom: "100%",
                    ease: Expo.easeInOut,

                });
                TweenMax.to(jQuery(".loader-wrap"), 0.8, {
                    force3D: true,
                    bottom: "100%",
                    ease: Expo.easeInOut,
                    delay: 0.2,

                });
                setTimeout(function () {
                    initpageloadAnimation();
                }, 600);
            }
        });
        var chdpt = jQuery(".content-holder").data("pagetitle");
        jQuery(".page-load_bg span").text(chdpt);
    }
    //   Background image ------------------
    var a = jQuery(".bg");
    a.each(function (a) {
        if (jQuery(this).attr("data-bg")) jQuery(this).css("background-image", "url(" + jQuery(this).data("bg") + ")");
    });
    //   clone ------------------
    jQuery.fn.duplicate = function (a, b) {
        var c = [];
        for (var d = 0; d < a; d++) jQuery.merge(c, this.clone(b).get());
        return this.pushStack(c);
    };
    jQuery("<div class='container full-height'></div>").appendTo(".sec-lines");
    jQuery("<div class='line-item'></div>").duplicate(5).appendTo(".sec-lines .container");
    //   Isotope------------------
    function n() {
        if (jQuery(".gallery-items").length) {
            var jQuerygrid = jQuery(".gallery-items").isotope({
                singleMode: true,
                columnWidth: ".grid-sizer, .grid-sizer-second, .grid-sizer-three",
                itemSelector: ".gallery-item, .gallery-item-second, .gallery-item-three",
                transformsEnabled: true,
                transitionDuration: "700ms",
            });
            jQuerygrid.imagesLoaded(function () {
                jQuerygrid.isotope("layout");
            });
            jQuery(".gallery-filters").on("click", "a.gallery-filter", function (b) {
                b.preventDefault();
                var c = jQuery(this).attr("data-filter"),
                    d = jQuery(this).text();
                jQuerygrid.isotope({
                    filter: c
                });
                jQuery(".gallery-filters a").removeClass("gallery-filter-active");
                jQuery(this).addClass("gallery-filter-active");
            });
            var gat = jQuery(".gallery-filter-active").text();
        }
        jQuery(".gallery-items").isotope("on", "layoutComplete", function (a, b) {
            var b = a.length;
            jQuery(".num-album").html(b);
        });
        var b = jQuery(".gallery-item").length;
        jQuery(".all-album , .num-album").html(b);
    }
    n();
   //  swiper ------------------
    if (jQuery(".home-half-slider").length > 0) {
        var j = new Swiper(".fs-gallery-wrap .swiper-container", {
            preloadImages: false,
            loop: true,
            grabCursor: true,
            centeredSlides: false,
            resistance: true,
            resistanceRatio: 0.6,
            speed: 1400,
            spaceBetween: 0,
            parallax: false,
            effect: "slide",
            mousewheel: false,
            pagination: {
                el: '.hero-slider-wrap_pagination',
                clickable: true,
            },
            autoplay: {
                delay: 4000,
                disableOnInteraction: false
            },
            navigation: {
                nextEl: '.hsc-next',
                prevEl: '.hsc-prev',
            },
        });
        j.on('slideChange', function () {
            var csli = j.realIndex + 1,
                curnum = jQuery('#current');
            TweenMax.to(curnum, 0.2, {
                force3D: true,
                y: -10,
                opacity: 0,
                ease: Power2.easeOut,
                onComplete: function () {
                    TweenMax.to(curnum, 0.1, {
                        force3D: true,
                        y: 10
                    });
                    curnum.html('0' + csli);
                }
            });
            TweenMax.to(curnum, 0.2, {
                force3D: true,
                y: 0,
                delay: 0.3,
                opacity: 1,
                ease: Power2.easeOut
            });
        });
        kpsc();
        j.on("slideChangeTransitionStart", function () {
            eqwe();
        });
        j.on("slideChangeTransitionEnd", function () {
            kpsc();
        });
        var totalSlides = j.slides.length - 2;
        jQuery('#total').html('0' + totalSlides);
        var imageSwiper = new Swiper(".hero-slider-img .swiper-container", {
            preloadImages: false,
            loop: true,
            resistance: true,
            direction: 'vertical',
            spaceBetween: 10,
            effect: "slide",
        });
        j.controller.control = imageSwiper;
        imageSwiper.controller.control = j;
    }
    function kpsc() {
        jQuery(".slide-progress").css({
            width: "100%",
            transition: "width 3000ms"
        });
    }
    function eqwe() {
        jQuery(".slide-progress").css({
            width: 0,
            transition: "width 0s"
        });
    }
    if (jQuery(".testimonilas-carousel").length > 0) {
        var j2 = new Swiper(".testimonilas-carousel .swiper-container", {
            preloadImages: false,
            slidesPerView: 2,
            spaceBetween: 20,
            loop: true,
            grabCursor: true,
            mousewheel: false,
            centeredSlides: false,
            pagination: {
                el: '.tc-pagination',
                clickable: true,
                dynamicBullets: true,
            },
            navigation: {
                nextEl: '.tcb-next',
                prevEl: '.tcb-prev',
            },
            breakpoints: {

                800: {
                    slidesPerView: 1,
                },
            }
        });
    }
    if (jQuery(".fw-carousel").length > 0) {
        var totalSlides2 = jQuery(".fw-carousel .swiper-slide").length;
        var mouseContr = jQuery(".fw-carousel").data("mousecontrol");
        var j2 = new Swiper(".fw-carousel .swiper-container", {
            preloadImages: false,
            loop: true,
            freeMode: true,
            slidesPerView: 'auto',
            spaceBetween: 20,
            grabCursor: true,
            mousewheel: mouseContr,
            speed: 1400,

            effect: "slide",
            pagination: {
                el: '.fw-carousel_pagination',
                clickable: true,
            },
            navigation: {
                nextEl: '.fw-carousel-button-next',
                prevEl: '.fw-carousel-button-prev',
            },
        });
    }
    if (jQuery(".fs-slider").length > 0) {
        var mouseContr2 = jQuery(".fs-slider").data("mousecontrol2");
        var j3 = new Swiper(".fs-slider .swiper-container", {
            preloadImages: false,
            loop: true,
            grabCursor: true,
            speed: 1400,
            spaceBetween: 0,
            effect: "slide",
            mousewheel: mouseContr2,
            pagination: {
                el: '.hero-slider-wrap_pagination',
                clickable: true,
            },
            navigation: {
                nextEl: '.hsc-next',
                prevEl: '.hsc-prev',
            },
        });
    }
    if (jQuery(".single-slider").length > 0) {
        var j2 = new Swiper(".single-slider .swiper-container", {
            preloadImages: false,
            slidesPerView: 1,
            spaceBetween: 0,
            loop: true,
            autoHeight: true,
            grabCursor: true,
            mousewheel: false,
            pagination: {
                el: '.ss-slider-pagination',
                clickable: true,
            },
            navigation: {
                nextEl: '.ss-slider-cont-next',
                prevEl: '.ss-slider-cont-prev',
            },
        });
    }
    if (jQuery(".multi-slideshow_fs").length > 0) {
        var ms1 = new Swiper(".multi-slideshow_fs .swiper-container", {
            preloadImages: false,
            loop: true,
            speed: 1400,
            spaceBetween: 0,
            effect: "fade",
            autoplay: {
                delay: 2500,
                disableOnInteraction: false
            },
        });
    }
    if (jQuery(".grid-carousel ").length > 0) {
        var totalSlides2 = jQuery(".grid-carousel .swiper-slide").length;
        var gridCarusel = new Swiper(".grid-carousel .swiper-container", {
            preloadImages: false,
            loop: true,
            freeMode: false,
            slidesPerView: 3,
            spaceBetween: 10,
            grabCursor: true,
            mousewheel: false,
            speed: 1400,
            effect: "slide",
            autoplay: {
                delay: 3000,
                disableOnInteraction: false
            },
            navigation: {
                nextEl: '.ss-slider-cont-next',
                prevEl: '.ss-slider-cont-prev',
            },
            breakpoints: {
                1068: {
                    slidesPerView: 2,
                },
                640: {
                    slidesPerView: 1,
                },
            }
        });
    }
    jQuery(".carousel-title-wrap").on({
        mouseenter: function () {
            jQuery(this).parents(".swiper-slide").find(".bg").addClass("hov-rot");
        },
        mouseleave: function () {
            jQuery(this).parents(".swiper-slide").find(".bg").removeClass("hov-rot");
        }
    });
    //   lightGallery------------------
    function lightGalleryInit() {
        jQuery(".image-popup").lightGallery({
            selector: "this",
            cssEasing: "cubic-bezier(0.25, 0, 0.25, 1)",
            download: false,
            counter: false
        });
        var o = jQuery(".lightgallery"),
            p = o.data("looped");
        o.lightGallery({
            selector: ".lightgallery a.popup-image",
            cssEasing: "cubic-bezier(0.25, 0, 0.25, 1)",
            download: false,
            loop: false,
            counter: false
        });
    }
    lightGalleryInit();
    //   appear------------------
    jQuery(".stats").appear(function () {
        jQuery(".num").countTo();
    });
    jQuery(".piechart-holder").appear(function () {
        jQuery(this).find(".chart").each(function () {
            var cbc = jQuery(".piechart-holder").attr("data-skcolor");
            jQuery(".chart").easyPieChart({
                barColor: cbc,
                trackColor: "#292929",
                scaleColor: "#292929",
                size: "150",
                lineWidth: "40",
                lineCap: "butt",
                animate: 3500,
                easing: "easeInBounce",
                onStep: function (a, b, c) {
                    jQuery(this.el).find(".percent").text(Math.round(c));
                }
            });
        });
    });
    jQuery(".skillbar-box").appear(function () {
        jQuery(this).find("div.skillbar-bg").each(function () {
            jQuery(this).find(".custom-skillbar").delay(600).animate({
                width: jQuery(this).attr("data-percent")
            }, 1500);
        });
    });
    //   accordion ------------------
    jQuery(".accordion a.toggle").on("click", function (a) {
        a.preventDefault();
        jQuery(".accordion a.toggle").removeClass("act-accordion");
        jQuery(this).addClass("act-accordion");
        if (jQuery(this).next('div.accordion-inner').is(':visible')) {
            jQuery(this).next('div.accordion-inner').slideUp();
        } else {
            jQuery(".accordion a.toggle").next('div.accordion-inner').slideUp();
            jQuery(this).next('div.accordion-inner').slideToggle();
        }
    });
    //  Map------------------	
    if (jQuery("#map-single").length > 0) {
        var latlog = jQuery('#map-single').data('latlog'),
            popupTextit = jQuery('#map-single').data('popuptext'),
            map = L.map('map-single').setView(latlog, 15);
        L.tileLayer('http://{s}.tiles.wmflabs.org/bw-mapnik/{z}/{x}/{y}.png', {
            attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
        }).addTo(map);
        var greenIcon = L.icon({
            iconUrl: jQuery('#map-single').data('popupicon'),
            iconSize: [40, 40],
            popupAnchor: [0, -26]
        });
        L.marker(latlog, {
            icon: greenIcon
        }).addTo(map).bindPopup(popupTextit).openPopup();
    }
    //   Contact form------------------
    jQuery("#contactform").submit(function () {
        var a = jQuery(this).attr("action");
        jQuery("#message").slideUp(750, function () {
            jQuery("#message").hide();
            jQuery("#submit").attr("disabled", "disabled");
            jQuery.post(a, {
                name: jQuery("#name").val(),
                email: jQuery("#email").val(),
                phone: jQuery("#phone").val(),
                subject: jQuery('#subject').val(),
                comments: jQuery("#comments").val(),
                verify: jQuery('#verify').val()

            }, function (a) {
                document.getElementById("message").innerHTML = a;
                jQuery("#message").slideDown("slow");
                jQuery("#submit").removeAttr("disabled");
                if (null != a.match("success")) jQuery("#contactform").slideDown("slow");
            });
        });
        return false;
    });
    jQuery("#contactform input, #contactform textarea").keyup(function () {
        jQuery("#message").slideUp(1500);
    });
    //   mailchimp------------------
    jQuery("#subscribe").ajaxChimp({
        language: "eng",
        url: jQuery('#subscribe').data('chimplist'),
    });
    jQuery.ajaxChimp.translations.eng = {
        submit: "Submitting...",
        0: '<i class="fa fa-check"></i> We will be in touch soon!',
        1: '<i class="fa fa-warning"></i> You must enter a valid e-mail address.',
        2: '<i class="fa fa-warning"></i> E-mail address is not valid.',
        3: '<i class="fa fa-warning"></i> E-mail address is not valid.',
        4: '<i class="fa fa-warning"></i> E-mail address is not valid.',
        5: '<i class="fa fa-warning"></i> E-mail address is not valid.'
    };
    function videoint() {
        //   Video------------------
        var v = jQuery(".background-youtube-wrapper").data("vid");
        var f = jQuery(".background-youtube-wrapper").data("mv");
        jQuery(".background-youtube-wrapper").YTPlayer({
            fitToBackground: true,
            videoId: v,
            pauseOnScroll: true,
            mute: f,
            callback: function () {
                var a = jQuery(".background-youtube-wrapper").data("ytPlayer").player;
            }
        });
        var vid = jQuery(".background-vimeo").data("vim");
        jQuery(".background-vimeo").append('<iframe src="//player.vimeo.com/video/' + vid + '?background=1"  frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen ></iframe>');
        jQuery(".video-holder").height(jQuery(".media-container").height());
        if (jQuery(window).width() > 1024) {
            if (jQuery(".video-holder").size() > 0)
                if (jQuery(".media-container").height() / 9 * 16 > jQuery(".media-container").width()) {
                    jQuery(".background-vimeo iframe ").height(jQuery(".media-container").height()).width(jQuery(".media-container").height() / 9 * 16);
                    jQuery(".background-vimeo iframe ").css({
                        "margin-left": -1 * jQuery("iframe").width() / 2 + "px",
                  
                        "margin-top": "0px"
                    });
                } else {
                    jQuery(".background-vimeo iframe ").width(jQuery(window).width()).height(jQuery(window).width() / 16 * 9);
                    jQuery(".background-vimeo iframe ").css({
                        "margin-left": -1 * jQuery("iframe").width() / 2 + "px",
                        "margin-top": -1 * jQuery("iframe").height() / 2 + "px",
                        top: "50%"
                    });
                }
        } else if (jQuery(window).width() < 760) {
            jQuery(".video-holder").height(jQuery(".media-container").height());
            jQuery(".background-vimeo iframe ").height(jQuery(".media-container").height());
        } else {
            jQuery(".video-holder").height(jQuery(".media-container").height());
            jQuery(".background-vimeo iframe ").height(jQuery(".media-container").height());
        }
        jQuery(".video-container").css("width", jQuery(window).width() + "px");
        jQuery(".video-container").css("height", Number(720 / 1280 * jQuery(window).width()) + "px");
        if (jQuery(".video-container").height() < jQuery(window).height()) {
            jQuery(".video-container").css("height", jQuery(window).height() + "px");
            jQuery(".video-container").css("width", Number(1280 / 720 * jQuery(window).height()) + "px");
        }
    }
    videoint();
    // Share   ------------------
    jQuery(".share-container").share({
        networks: ['facebook', 'pinterest', 'twitter', 'linkedin']
    });
//   Parallax ------------------
    var jQueryone = jQuery(".mm-parallax"),
        browserPrefix = "",
        usrAg = navigator.userAgent;
    if (usrAg.indexOf("Chrome") > -1 || usrAg.indexOf("Safari") > -1) browserPrefix = "-webkit-";
    else if (usrAg.indexOf("Opera") > -1) browserPrefix = "-o";
    else if (usrAg.indexOf("Firefox") > -1) browserPrefix = "-moz-";
    else if (usrAg.indexOf("MSIE") > -1) browserPrefix = "-ms-";
    jQuery(".hero-wrap").mousemove(function (a) {
        var b = Math.ceil(window.innerWidth / 1.5),
            c = Math.ceil(window.innerHeight / 1.5),
            d = a.pageX - b,
            e = a.pageY - c,
            f = e / c,
            g = -(d / b),
            h = Math.sqrt(Math.pow(f, 2) + Math.pow(g, 2)),
            i = 10 * h;
        jQueryone.css(browserPrefix + "transform", "rotate3d(" + f + ", " + g + ", 0, " + i + "deg)");
    });
    //   Blog filter ------------------
    jQuery(".blog-btn").on("click", function () {
        jQuery(this).parent(".blog-btn-filter").find("ul").slideToggle(500);
        return false;
    });
    jQuery(".search-btn").on("click", function () {
        jQuery(this).toggleClass("visbs");
        jQuery(".blog-search-wrap").slideToggle(500);
        return false;
    });
 	function initpsn(){
    	var wwini = jQuery(window).width();
 			if (wwini > 1064){
				jQuery(".page-scroll-nav").trigger('detach.ScrollToFixed');
				jQuery(".page-scroll-nav").scrollToFixed({
					zIndex: 212,
					marginTop: 0,
					removeOffsets: true,
					limit: function () {
						var a = jQuery(".limit-box").offset().top - jQuery(".page-scroll-nav").outerHeight(true);
						return a;
					}
				});			
			}
 			else {
				jQuery(".page-scroll-nav").trigger('detach.ScrollToFixed');
				jQuery(".page-scroll-nav").scrollToFixed({
					zIndex: 212,
					marginTop: 70,
					removeOffsets: true,
					limit: function () {
						var a = jQuery(".limit-box").offset().top - jQuery(".page-scroll-nav").outerHeight(true);
						return a;
					}
				});				
			}
 	}
	initpsn();
	
//   scroll to fixed ------------------	
    jQuery(".fixed-column-wrap").scrollToFixed({
        minWidth: 1064,
        zIndex: 12,
        marginTop: 0,
        removeOffsets: true,
        limit: function () {
            var a = jQuery(".limit-box").offset().top - jQuery(".fixed-column-wrap").outerHeight(true);
            return a;
        }
    });
    jQuery(".fixed-top-panel").scrollToFixed({
        minWidth: 1064,
        zIndex: 112,
        marginTop: 0,
        removeOffsets: true,
        limit: function () {
            var a = jQuery(".limit-box").offset().top - jQuery(".fixed-top-panel").outerHeight(true);
            return a;
        }
    });
    jQuery(".project-details").scrollToFixed({
        minWidth: 1064,
        zIndex: 5,
        marginTop: 85,
        removeOffsets: true,
        limit: function () {
            var a = jQuery(".limit-box2").offset().top - jQuery(".project-details").outerHeight(true);
            return a;
        }
    });
    jQuery('.hero-decor-let').rotaterator({
        fadeSpeed: 500,
        pauseSpeed: 1200
    });
    var jQuerywindow = jQuery(window);
    // Styles ------------------
    function csselem() {
        jQuery(".height-emulator").css({
            height: jQuery(".fixed-footer").outerHeight(true)
        });
        jQuery(".show-case-slider .show-case-item").css({
            height: jQuery(".show-case-slider").outerHeight(true)
        });
        jQuery(".fixed-column-wrap").css({
            height: jQuerywindow.outerHeight(true) - 1 + "px"
        });
        jQuery(".half-slider-item").css({
            height: jQuery(".half-slider-wrap").outerHeight(true)
        });
        jQuery(".half-slider-img-item").css({
            height: jQuery(".half-slider-img").outerHeight(true)
        });
        jQuery(".fs-slider-item").css({
            height: jQuery(".fs-slider-wrap").outerHeight(true)
        });
        jQuery(".ms-item_fs").css({
            height: jQuery(".multi-slideshow_fs").outerHeight(true)
        });
    }
    csselem();
    jQuerywindow.resize(function () {
        csselem();
		initpsn();
    });
    // Counter ------------------
    if (jQuery(".counter-widget").length > 0) {
        var countCurrent = jQuery(".counter-widget").attr("data-countDate");
        jQuery(".countdown").downCount({
            date: countCurrent,
            offset: 0
        });
    }
    jQuerywindow.on("scroll", function (a) {
        var a = jQuery(document).height();
        var b = jQuery(window).height();
        var c = jQuery(window).scrollTop();
        var d = c / (a - b) * 100;
        jQuery(".progress-bar").css({
            width: d + "%"
        });
    });
//  scroll nav ------------------	
    var bgi2 = jQuery(".fbgs").data("bgscr");
    var bgt2 = jQuery(".fbgs").data("bgtex");
    jQuery(".bg-scroll").css("background-image", "url(" + bgi2 + ")");
    jQuery(".bg-title span").html(bgt2);
    jQuery(".scroll-init ul").singlePageNav({
        filter: ":not(.external)",
        updateHash: false,
        offset: 70,
        threshold: 120,
        speed: 1200,
        currentClass: "actscr-link"
    });
    //   scroll to------------------
    jQuery(".custom-scroll-link").on("click", function () {
        var a = 80;
        if (location.pathname.replace(/^\//, "") === this.pathname.replace(/^\//, "") || location.hostname === this.hostname) {
            var b = jQuery(this.hash);
            b = b.length ? b : jQuery("[name=" + this.hash.slice(1) + "]");
            if (b.length) {
                TweenLite.to(jQuery("html,body"), 1, {
                    scrollTo: {
                        y: b.offset().top,
                        offsetY: 80,
                        autoKill: false
                    }
                });
                return false;

            }
        }
    });
    jQuery(".to-top").on("click", function () {
        TweenLite.to(window, 2, {
            scrollTo: {
                y: 0,
                offsetY: 0,
                autoKill: false
            }
        });
    });
    jQuery(".scroll-con-sec").ctscroll();
    jQuery(".arrowpagenav a").on("click", function (a) {
        a.preventDefault();
    });
    // twitter ------------------
    if (jQuery("#twitts-container").length > 0) {
        var config1 = {
            "profile": {
                "screenName": jQuery('#twitts-container').data('profilename'),
            },
            "domId": 'twitts-container',
            "maxTweets": 2,
            "enableLinks": true,
            "showImages": false
        };
        twitterFetcher.fetch(config1);
    }
//   cursor ------------------	
    jQuery("a , .btn ,   textarea,   input , .single-carousel-control_list li , .sb-button , .share-btn").on({
        mouseenter: function () {
            TweenMax.to('.element-item ', 0.4, {
                borderColor: 'transparent',
                scale: 0.5,
                background: jQuery('.element-item').data('mouseback'),
                opacity: 0.6,
                left: 0,
                top: 0
            });
            jQuery(".element-item ").addClass("nocircle");
        },
        mouseleave: function () {
            TweenMax.to('.element-item ', 0.4, {
                borderColor: jQuery('.element-item').data('mouseborder'),
                scale: 1.0,
                background: "none",
                opacity: 1,
            });
            jQuery(".element-item ").removeClass("nocircle");
        }
    });
    jQuery(".nav-overlay").on({
        mouseenter: function () {
            TweenMax.to('.element-item ', 0.4, {
                transformOrigin: '35px 35px',
                borderWidth: '1px',
                borderColor: '#fff',
                scale: 1.8,
                left: 23,
                top: 23
            });
            jQuery(".element-item").addClass("closeicon");
        },
        mouseleave: function () {
            TweenMax.to('.element-item ', 0.4, {
                transformOrigin: '30px 30px',
                borderWidth: '2px',
                borderColor: jQuery('.element-item').data('mouseborder'),
                scale: 1.0,
                left: 0,
                top: 0
            });
            jQuery(".element-item").removeClass("closeicon");
        }
    });
    jQuery(".swiper-container , .horizontal-grid-wrap").on({
        mouseenter: function () {
            TweenMax.to('.element-item ', 0.4, {
                transformOrigin: '35px 35px',
                borderWidth: '1px',
                borderColor: jQuery('.element-item').data('mouseborder'),
                scale: 1.8,
                left: 23,
                top: 23
            });
            jQuery(".element-item").addClass("swipericon");
        },
        mouseleave: function () {
            TweenMax.to('.element-item ', 0.4, {
                transformOrigin: '30px 30px',
                borderWidth: '2px',
                 borderColor: jQuery('.element-item').data('mouseborder'),
                scale: 1.0,
                left: 0,
                top: 0
            });
            jQuery(".element-item").removeClass("swipericon");
        }
    });
    jQuery(".swiper-container a.box-media-zoom").on({
        mouseleave: function () {
            TweenMax.to('.element-item ', 0.4, {
                transformOrigin: '35px 35px',
                borderWidth: '1px',
                borderColor: jQuery('.element-item').data('mouseborder'),
                scale: 1.8,
                left: 23,
                top: 23
            });
        }
    });
    jQuery(".gallery-item   .box-media-zoom , .gallery-item .thumb-info").on({
        mouseleave: function () {
            TweenMax.to('.element-item ', 0.4, {
                 borderColor: jQuery('.element-item').data('mouseborder'),
            });
        }
    });
    //  menu------------------			
    jQuery("#menu").menu();
    jQuery(".sliding-menu li a.nav").parent("li").addClass("submen-dec");
    jQuery(".nav-scroll-bar-wrap").niceScroll({
        cursorwidth: "0px",
        cursorborder: "none",
        cursorborderradius: "0px",
    });
    var nbw = jQuery(".nav-button"),
        nhw = jQuery(".nav-holder"),
        nho = jQuery(".nav-overlay"),
        nhd = jQuery(".nav-holder-dec"),
        tba = jQuery(".top-header");
    function showMenu() {
        nho.fadeIn(500);
        TweenMax.to(tba, 0.9, {
            force3D: false,
            top: "-100px",
            ease: Expo.easeInOut
        });
        TweenMax.to(nhd, 1.2, {
            force3D: false,
            left: "0",
            ease: Expo.easeInOut
        });
        TweenMax.to(nhw, 1.2, {
            force3D: false,
            left: "0",
            delay: 0.2,
            ease: Expo.easeInOut
        });
        nhw.removeClass("but-hol");
        nbw.addClass("cmenu");
    }
    function hideMenu() {
        TweenMax.to(nhw, 1.2, {
            force3D: false,
            left: "-100%",
            ease: Expo.easeInOut
        });
        TweenMax.to(nhd, 1.2, {
            force3D: false,
            left: "-100%",
            delay: 0.2,
            ease: Expo.easeInOut
        });
        TweenMax.to(tba, 0.9, {
            force3D: false,
            top: "0",
            ease: Expo.easeInOut,
            delay: 0.6
        });
        nhw.addClass("but-hol");
        nbw.removeClass("cmenu");
        nho.fadeOut(500);
    }
    nbw.on("click", function () {
        if (nhw.hasClass("but-hol")) showMenu();
        else hideMenu();
    });
    nho.on("click", function () {
        hideMenu();
    });
}
function initpageloadAnimation() {
    TweenMax.to(jQuery(".pr-bg"), 1.3, {
        force3D: true,
        left: "100%",
        ease: Expo.easeInOut,
    });
    TweenMax.to(jQuery(".fcw-dec"), 1.0, {
        force3D: true,
        left: "100%",
        ease: Expo.easeInOut,
        onComplete: function () {
            TweenMax.to(jQuery(".fcw-title"), 1.2, {
                force3D: true,
                y: 0,
                opacity: "1",
                ease: Power2.easeOut
            });
        }
    });
    TweenMax.to(jQuery(".sin-anim"), 1.2, {
        force3D: true,
        delay: 1.0,
        y: 0,
        opacity: "1",
        ease: Power2.easeOut
    });
    TweenMax.to(jQuery(".fixed-top-panel"), 1.2, {
        force3D: true,
        y: 0,
        delay: 0.4,
        ease: Expo.easeInOut
    });
    TweenMax.to(jQuery(".bot-element  "), 1.2, {
        force3D: true,
        delay: 1.0,
        x: 0,
        opacity: "1",
        ease: Power2.easeOut
    });
    jQuery(".hiddec-anim").each(function (ac) {
        var bp = jQuery(this);
        setTimeout(function () {
            TweenMax.to(bp, 0.9, {
                force3D: true,
                x: 0,
                opacity: "1",
                delay: 0.3,
                ease: Expo.easeInOut
            });
        }, 230 * ac);
    });
}
//   load animation------------------
jQuery("<div class='page-load'><div class='page-load_bg'><span></span></div><div class='page-load_bg2 color-bg'></div></div>").appendTo("#main");
function contentAnimShow() {
    TweenMax.to(jQuery(".page-subtitle strong"), 0.9, {
        force3D: true,
        y: -100,
        opacity: 0,
        delay: 0.7,
        ease: Power2.easeOut,
        onComplete: function () {
            TweenMax.to(jQuery(".page-subtitle strong"), 0.1, {
                force3D: true,
                y: 100
            });
        }
    });
    jQuery(".lg-backdrop , .lg-outer").remove();
    jQuery(".nav-button").removeClass("cmenu");
    jQuery(".page-load").fadeIn(1);
    TweenMax.to(jQuery(".page-load_bg2"), 0.8, {
        force3D: true,
        top: "0",
        ease: Expo.easeInOut
    });
    TweenMax.to(jQuery(".page-load_bg"), 0.9, {
        force3D: true,
        top: "0",
        delay: 0.3,
        ease: Expo.easeInOut
    });
    setTimeout(function () {
        jQuery("html, body").animate({
            scrollTop: 0
        }, {
            queue: true,
            duration: 10,
        });
    }, 1000);
}
function contentAnimHide() {
    var chdpt = jQuery(".content-holder").data("pagetitle");
    jQuery(".page-load_bg span").text(chdpt);
    TweenMax.to(jQuery(".page-load_bg span"), 0.6, {
        force3D: true,
        y: 0,
        opacity: 1,
        ease: Power4.easeNone,
        onComplete: function () {
            TweenMax.to(jQuery(".page-load_bg span"), 0.5, {
                force3D: true,
                y: -150,
                opacity: 0,
                delay: 0.2,
                ease: Power4.easeNone
            });
        }
    });
    setTimeout(function () {
        initpageloadAnimation();
    }, 1800);
    setTimeout(function () {
        TweenMax.to(jQuery(".page-load_bg"), 0.8, {
            force3D: true,
            bottom: "100%",
            ease: Expo.easeInOut
        });
        TweenMax.to(jQuery(".page-load_bg2"), 0.9, {
            force3D: true,
            bottom: "100%",
            delay: 0.2,
            ease: Expo.easeInOut,
            onComplete: function () {
                setTimeout(function () {
                    jQuery(".page-load").fadeOut(1);
                    TweenMax.to(jQuery(".page-load_bg2 , .page-load_bg"), 0.0, {
                        force3D: true,
                        bottom: "0",
                        top: "100%"
                    });
                    TweenMax.to(jQuery(".page-load_bg span"), 0, {
                        y: 150,
                        opacity: 0,
                    });
                }, 10);
            }
        });
    }, 1100);
}
//   Parallax ------------------
function initparallax() {
    var a = {
        Android: function () {
            return navigator.userAgent.match(/Android/i);
        },
        BlackBerry: function () {
            return navigator.userAgent.match(/BlackBerry/i);
        },
        iOS: function () {
            return navigator.userAgent.match(/iPhone|iPad|iPod/i);
        },
        Opera: function () {
            return navigator.userAgent.match(/Opera Mini/i);
        },
        Windows: function () {
            return navigator.userAgent.match(/IEMobile/i);
        },
        any: function () {
            return a.Android() || a.BlackBerry() || a.iOS() || a.Opera() || a.Windows();
        }
    };
    trueMobile = a.any();
    if (null === trueMobile) {
        var b = new Scrollax();
        b.reload();
        b.init();
        var dotsCanvas = {
            init: function () {
                var jQueryblocks = jQuery('[data-dots]');
                jQueryblocks.each(function () {
                    var jQueryblock = jQuery(this);
                    var block = jQueryblock[0];
                    var jQuerycanvas = jQuery("<canvas/>").appendTo(jQueryblock);
                    var canvas = jQuerycanvas[0];
                    var width = jQueryblock.width();
                    var height = jQueryblock.height();
                    var ctx = canvas.getContext('2d');
                    ctx.width = width;
                    ctx.height = height;
                    var devicePixelRatio = window.devicePixelRatio || 1,
                        backingStoreRatio = ctx.webkitBackingStorePixelRatio || ctx.mozBackingStorePixelRatio || ctx.msBackingStorePixelRatio || ctx.oBackingStorePixelRatio || ctx.backingStorePixelRatio || 1;
                    var ratio = devicePixelRatio / backingStoreRatio;
                    canvas.width = width * ratio;
                    canvas.height = height * ratio;
                    ctx.scale(ratio, ratio);
                    var mouseX = undefined;
                    var mouseY = undefined;

                    function Circle(x, y) {
                        this.x = x;
                        this.y = y;
                        this.distance = 10;
                        this.radians = 0;
                        this.draw = function () {
                            ctx.beginPath();
                            ctx.strokeStyle = 'rgba(151, 151, 151, .3)';
                            ctx.moveTo(this.x + 3, this.y);
                            ctx.lineTo(this.x + 3, this.y + 6);
                            ctx.moveTo(this.x, this.y + 3);
                            ctx.lineTo(this.x + 6, this.y + 3);
                            ctx.stroke();
                        };
                        this.update = function () {
                            if (mouseX > -1) {
                                var k1 = mouseY - y;
                                var k2 = mouseX - x;
                                var tan = k1 / k2;
                                var yrad = Math.atan(tan);
                                if (mouseX < x) {
                                    yrad = Math.PI - Math.atan(-tan);
                                }
                                this.x = x + Math.cos(yrad) * this.distance;
                                this.y = y + Math.sin(yrad) * this.distance;
                            }
                            this.draw();
                        };
                    };
                    var circlesArray = [];
                    var gutter = 40;
                    var countW = Math.floor(width / gutter);
                    var countH = Math.floor(height / gutter);
                    var len = countW * countH;
                    for (var i = 0; i < countH; i++) {
                        for (var t = 0; t < countW; t++) {
                            var x = gutter * t;
                            var y = gutter * i;
                            circlesArray.push(new Circle(x, y));
                        }

                    }
                    var loop = function () {
                        ctx.clearRect(0, 0, ctx.width, ctx.height);
                        for (var i = 0; i < circlesArray.length; i++) {
                            circlesArray[i].update();
                        }
                    };
                    document.addEventListener('mousemove', function (e) {
                        var parentOffset = jQuery(canvas).parent().offset();
                        var relX = e.pageX - parentOffset.left;
                        var relY = e.pageY - parentOffset.top;
                        mouseX = relX;
                        mouseY = relY;
                        ctx.clearRect(0, 0, ctx.width, ctx.height);
                        for (var i = 0; i < circlesArray.length; i++) {
                            circlesArray[i].update();
                        }
                        loop();
                    });
                    loop();
                });
            }
        };
        window.requestAnimationFrame = (function () {
            return window.requestAnimationFrame || window.webkitRequestAnimationFrame || window.mozRequestAnimationFrame || function (callback) {
                window.setTimeout(callback, 1000 / 60);
            };
        })();
        window.cancelAnimationFrame = (function () {
            return window.cancelAnimationFrame || window.webkitCancelAnimationFrame || window.mozCancelAnimationFrame || function (timPtr) {
                window.clearTimeout(timPtr);
            };
        })();
        dotsCanvas.init();
    }
    if (trueMobile) jQuery(".bgvid , .background-vimeo , .background-youtube-wrapper  , .gallery__dots").remove();
}
var mouse = {
    x: 0,
    y: 0
};
var pos = {
    x: 0,
    y: 0
};
var ratio = 0.15;
var active = false;
var ball = document.querySelector('.element-item');
TweenLite.set(ball, {
    xPercent: -50,
    yPercent: -50
});
document.addEventListener("mousemove", mouseMove);
function mouseMove(e) {
    var scrollTop = window.pageYOffset || document.documentElement.scrollTop;
    mouse.x = e.pageX;
    mouse.y = e.pageY - scrollTop;
}
TweenMax.ticker.addEventListener("tick", updatePosition);
function updatePosition() {
    if (!active) {
        pos.x += (mouse.x - pos.x) * ratio;
        pos.y += (mouse.y - pos.y) * ratio;
        TweenMax.set(ball, {
            x: pos.x,
            y: pos.y
        });
    }
}
//   clone ------------------
jQuery.fn.duplicate = function (a, b) {
    var c = [];
    for (var d = 0; d < a; d++) jQuery.merge(c, this.clone(b).get());
    return this.pushStack(c);
};
jQuery("<span class='folio-btn-dot'></span>").duplicate(9).appendTo(".folio-btn-item");
//   Init Ajax------------------
jQuery(function () {
    jQuery.coretemp({
        reloadbox: "#wrapper",
        outDuration: 700,
        inDuration: 200
    });
    readyFunctions();
    jQuery(document).on({
        ksctbCallback: function () {
            readyFunctions();
        }
    });
});

function initajaxload () {
}
function inittitlereplace () {
}
function initmenuajaxdisable () {
	jQuery(".menu-item-has-children > a").each(function(i){
	jQuery(this).removeClass('ajax');
	})
}
//   Init All Functions------------------
function readyFunctions() {
    initparallax();
    initNastik();
	initajaxload ();
	inittitlereplace ();
	initmenuajaxdisable ();
}