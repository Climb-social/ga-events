<!DOCTYPE html>
<html lang="en">

    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">

        <title>Climb.social | Worklife | {{ page.title }}</title>

        <meta content="Climb.social | Worklife | {{ page.title }}" name="description">
        <meta name="viewport" content="width = device-width, initial-scale = 1.0" />
        <meta name="author" content="Climb.social">
        <script class="rs-file" src="../assets/royalslider/jquery-1.8.3.min.js"></script>
        <script class="rs-file" src="../assets/royalslider/jquery.royalslider.min.js"></script>
        <link class="rs-file" href="../assets/royalslider/royalslider.css" rel="stylesheet">
        <link class="rs-file" href="../assets/royalslider/skins/minimal-white/rs-minimal-white.css" rel="stylesheet">
        <link href='https://fonts.googleapis.com/css?family=Karla:400,400italic,700' rel='stylesheet' type='text/css'>
        <link href="../assets/styles/main.css" rel="stylesheet">
        <style>
            body {
                background-image: linear-gradient(rgba(0, 0, 0, 0.701961), rgba(0, 0, 0, 0.701961)), url("{{ page.background }}");
            }
            .rsSlide {
                background-image: linear-gradient(rgba(0, 0, 0, 0.701961), rgba(0, 0, 0, 0.701961)), url("{{ page.background }}") !important;
            }
            .message:after {
                content: "{{ page.hashtag }}";
            }

            .message::before {
                content: "{{ page.wifi }}";
            }
        </style>
    </head>

    <body>
        <div class="sliderContainer fullWidth clearfix">
            <div id="full-width-slider" class="royalSlider heroSlider rsMinW">
                <div class="rsContent message">
                    <div class="center">

                        <h3>{{ page.title }}</h3>
                        <div class="speakers">

                            {% for speaker in page.speakers %}
                                <div class="speaker">
                                    <img src="{{ speaker.image }}">
                                    <h4>{{ speaker.name }}</h4>
                                    <span>{{ speaker.position }}</span>
                                </div>
                            {% endfor %}
                        </div>
                    </div>
                    <div class="footer">
                        <div>
                            {% for sponsor in page.sponsors %}
                        		<img class="sponsor-logo" src="{{ sponsor.logo }}">
                            {% unless forloop.last %}<span>+</span> {% endunless %}{% endfor %}

                        </div>
                        <img class="sponsor-logo" src="../assets/img/climb_powered-by.png">
                    </div>
                </div>
                <div class="rsContent message">
                    <div class="climb-feed">
                        <div class="climb-slideshow" data-collection-id="{{ page.collectionid }}" data-delay="7"></div>
                    </div>
                    <div class="footer">
                        <div>
                            {% for sponsor in page.sponsors %}
                        		<img class="sponsor-logo" src="{{ sponsor.logo }}">
                            {% unless forloop.last %}<span>+</span> {% endunless %}{% endfor %}

                        </div>
                        <img class="sponsor-logo" src="../assets/img/climb_powered-by.png">
                    </div>
                </div>
            </div>
        </div>
        <script id="addJS">
            jQuery(document).ready(function($) {
                $('#full-width-slider').royalSlider({
                    transitionType: 'fade',
                    keyboardNavEnabled: true,
                    fullscreen: {
                        enabled: true,
                        buttonFS: false,
                        nativeFS: false
                    },

                    startSlideId: 0,

                    controlNavigation: 'none'
                });

                var slider = $('#full-width-slider').data('royalSlider');
                slider.enterFullscreen();
            });
        </script>
        <script src="//fb.me/react-0.14.0.min.js"></script>
        <script src="//fb.me/react-dom-0.14.0.min.js"></script>
        <script src="//cdn.rawgit.com/climb-social/react-climb-social/v1.2.0/dist/react-climb-social.min.js"></script>
    </body>

</html>