<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Counterspell Game Jam Austria - Hack Club</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" rel="stylesheet">
    <link rel="stylesheet" type="text/css" href="./style.css" />
</head>
<body>
    <header class="header">
        <img src="https://assets.hackclub.com/flag-orpheus-top.svg" alt="Hack Club Logo" class="logo">
        <nav class="nav">
            <a href="#about">About</a>
            <a href="#location">Location</a>
            <a href="#schedule">Schedule</a>
            <a href="#sponsors">Sponsors</a>
            <a href="#faq">FAQ</a>
        </nav>
    </header>

    <main>
        <section id="hero" class="section hero">
            <div class="container">
                <h1>Counterspell Game Jam Austria 🇦🇹</h1>
                <p>Join us for an epic 12-hour game development adventure!</p>
                <a href="https://counterspell.hackclub.com/" class="cta-button" target="_blank">Register Now</a>
            </div>
        </section>

        <section id="about" class="section about">
            <div class="container">
                <div class="about-content">
                    <div class="about-text">
                        <h2>About Counterspell 🚀</h2>
                        <p>Counterspell is a beginner-friendly game jam for high schoolers happening in 200+ cities simultaneously. Whether you're an artist 🎨, musician 🎵, or coder 💻, come together to build amazing games in just 12 hours!</p>
                        <p>🍕 Free pizza and snacks for all participants!</p>
                        <p>🏆 Cool prizes and swag for the best games</p>
                    </div>
                    <div class="about-image">
                        <img alt="Game Jam Participants" src ="https://counterspell.hackclub.com/photos/3.png" />
                    </div>
                </div>
            </div>
        </section>

        <section id="location" class="section location">
            <div class="container">
                <h2>Event Location 📍</h2>
                <div class="blurred-map">
                    Location to be announced
                </div>
                <p>We're finalizing an awesome spot in Austria for our Game Jam. Stay tuned for the big reveal!</p>
            </div>
        </section>

        <section id="schedule" class="section schedule">
            <div class="container">
                <h2>Event Schedule ⏰</h2>
                <div class="schedule-grid">
                    <div class="schedule-item">
                        <h3>11:00 AM</h3>
                        <p>Doors open</p>
                    </div>
                    <div class="schedule-item">
                        <h3>12:00 PM</h3>
                        <p>Opening ceremony</p>
                    </div>
                    <div class="schedule-item">
                        <h3>12:30 PM</h3>
                        <p>Lunch & Team Formation</p>
                    </div>
                    <div class="schedule-item">
                        <h3>1:00 PM</h3>
                        <p>Start jamming!</p>
                    </div>
                    <div class="schedule-item">
                        <h3>7:00 PM</h3>
                        <p>Dinner & Mini-games</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="sponsors" class="section sponsors">
            <div class="container">
                <h2>Our Awesome Sponsors 🎉</h2>
                <div class="sponsor-logos">
                    <div class="sponsor-logo"></div>
                    <div class="sponsor-logo"></div>
                    <div class="sponsor-logo"></div>
                    <div class="sponsor-logo"></div>
                </div>
            </div>
        </section>

        <section id="faq" class="section faq">
            <div class="container">
                <h2>Frequently Asked Questions ❓</h2>
                <div class="faq-item">
                    <h3>Am I eligible to participate?</h3>
                    <p>If you're 18 or under, absolutely! If you're over 18 but still in high school, reach out to us at counterspell@hackclub.com.</p>
                </div>
                <div class="faq-item">
                    <h3>Is it really free?</h3>
                    <p>Yes, it's 100% free! We provide meals, snacks, and beverages throughout the event, plus you'll get cool swag and a chance to win prizes!</p>
                </div>
                <div class="faq-item">
                    <h3>What if I'm new to coding?</h3>
                    <p>No worries! We welcome all skill levels. We'll have workshops and mentors to help you learn and create awesome games.</p>
                </div>
                <div class="faq-item">
                    <h3>What should I bring?</h3>
                    <p>Bring your laptop, charger, and lots of creativity! If you have any specific hardware or software you prefer, feel free to bring that too.</p>
                </div>
            </div>
        </section>
    </main>

    <footer class="footer">
        <p>Built with ❤️ by teenagers, for teenagers at Hack Club</p>
        <div class="social-links">
            <a href="https://hackclub.com" target="_blank"><i class="fab fa-globe"></i></a>
            <a href="https://hackclub.slack.com" target="_blank"><i class="fab fa-slack"></i></a>
            <a href="https://youtube.com/hackclub" target="_blank"><i class="fab fa-youtube"></i></a>
            <a href="https://instagram.com/hackclub" target="_blank"><i class="fab fa-instagram"></i></a>
        </div>
    </footer>

    <script>
        let lastScrollTop = 0;
        const header = document.querySelector('.header');
        window.addEventListener('scroll', () => {
            const scrollTop = window.pageYOffset || document.documentElement.scrollTop;
            if (scrollTop > lastScrollTop) {
                header.classList.add('hidden');
            } else {
                header.classList.remove('hidden');
            }
            lastScrollTop = scrollTop;
        });

        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        document.querySelectorAll('.faq-item').forEach(item => {
            item.addEventListener('click', () => {
                item.classList.toggle('active');
            });
        });

        const observerOptions = {
            root: null,
            rootMargin: '0px',
            threshold: 0.1
        };

        const observer = new IntersectionObserver((entries, observer) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = 1;
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.section > .container').forEach(el => {
            el.style.opacity = 0;
            el.style.transform = 'translateY(50px)';
            el.style.transition = 'opacity 0.5s, transform 0.5s';
            observer.observe(el);
        });
    </script>
</body>
</html>
