html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kibera Safi Laundromat · Clean & fresh</title>
    <!-- Font Awesome 6 (free) for icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Roboto, system-ui, sans-serif;
        }

        body {
            background: #f0f4f8;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            padding: 1.5rem 1rem;
        }

        /* main card – business website */
        .laundry-card {
            max-width: 780px;
            width: 100%;
            background: white;
            border-radius: 2.5rem 2.5rem 2rem 2rem;
            box-shadow: 0 25px 45px -12px rgba(0, 40, 30, 0.35);
            overflow: hidden;
            border: 1px solid rgba(114, 185, 160, 0.2);
            transition: 0.25s;
        }

        /* hero image – simulates the uploaded photo with hilltop vibe + coke reference */
        .hero {
            background: #1e3b3a;  /* deep teal base, like a hilltop shadow */
            background-image: linear-gradient(125deg, #285c4b 0%, #1a3f32 45%, #344b3e 100%);
            position: relative;
            padding: 2.2rem 2rem 2.8rem 2rem;
            color: white;
            border-bottom: 6px solid #f7c35c; /* warm accent like old signage */
            box-shadow: inset 0 -8px 12px rgba(0,0,0,0.1);
            text-align: center;
        }

        /* the actual "photo" representation – like the uploaded IMG_0985.jpeg but stylised */
        .photo-placeholder {
            background: rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(2px);
            border-radius: 3.5rem 3.5rem 2rem 2rem;
            padding: 1.5rem 1.8rem 1.2rem 1.8rem;
            border: 2px dashed #f5e6d3;
            box-shadow: 0 12px 18px -8px rgba(0, 0, 0, 0.5);
            margin-bottom: 0.8rem;
            background-blend-mode: overlay;
            background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 200 120" opacity="0.2"><rect width="200" height="120" fill="none"/><text x="18" y="40" font-family="Arial" font-weight="bold" font-size="28" fill="%23fffaeb">HILLTOP</text><text x="32" y="80" font-family="Arial" font-size="38" fill="%23fffaeb" font-weight="800">LAUNDROMAT</text><text x="90" y="115" font-family="Arial" font-size="20" fill="%23ffe29c">Always Open</text></svg>');
            background-repeat: no-repeat;
            background-position: center;
            background-size: cover;
        }

        .photo-caption {
            font-size: 1.25rem;
            font-weight: 600;
            letter-spacing: 2px;
            color: #ffefc0;
            text-transform: uppercase;
            text-shadow: 3px 3px 0 #1a2e25;
            margin-top: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
        }

        .photo-caption i {
            font-size: 2rem;
            color: #f73b3b;  /* coca cola red accent */
            filter: drop-shadow(2px 2px 2px #260000);
        }

        .coke-no {
            background: #a82626;
            color: #fcf3d3;
            padding: 0.4rem 1.5rem;
            border-radius: 40px;
            font-weight: 800;
            font-size: 1.6rem;
            letter-spacing: 5px;
            display: inline-block;
            box-shadow: 0 6px 0 #561212;
            margin: 0.7rem 0 0.2rem;
            border: 1px solid #e0b8b8;
            transform: rotate(-0.5deg);
            font-family: 'Impact', 'Arial Black', sans-serif;
        }

        /* brand & message */
        .shop-name {
            background: #fcf9f2;
            padding: 1.8rem 2rem 1rem 2rem;
            text-align: center;
            border-bottom: 2px solid #c7e0d2;
        }

        .shop-name h1 {
            font-size: 2.8rem;
            font-weight: 900;
            letter-spacing: -0.5px;
            color: #1b4e3f;
            line-height: 1.2;
            text-shadow: 3px 3px 0 #e0f0e0;
        }

        .shop-name h1 i {
            color: #f09b43;
            font-size: 2.4rem;
            margin-right: 6px;
        }

        .shop-name .tagline {
            font-size: 1.5rem;
            font-weight: 500;
            color: #2a6b55;
            background: #e1f0e6;
            display: inline-block;
            padding: 0.4rem 2rem;
            border-radius: 60px;
            margin: 0.8rem 0 0.2rem;
        }

        /* contact section – with both numbers */
        .contact-block {
            padding: 2rem 2rem 2rem 2rem;
            background: #ffffff;
        }

        .two-numbers {
            display: flex;
            flex-wrap: wrap;
            gap: 1.2rem;
            justify-content: center;
            margin-bottom: 2rem;
        }

        .phone-card {
            background: linear-gradient(165deg, #f2faf5, #ffffff);
            flex: 1 1 200px;
            border: 1.5px solid #bcd9cc;
            border-radius: 38px;
            padding: 1.3rem 0.8rem;
            text-align: center;
            box-shadow: 6px 8px 0 #d0e3d8;
            transition: 0.15s;
        }

        .phone-card i {
            font-size: 2.2rem;
            background: #1b4e3f;
            color: white;
            padding: 0.8rem;
            border-radius: 50%;
            margin-bottom: 0.7rem;
            width: 4rem;
            height: 4rem;
            display: inline-flex;
            align-items: center;
            justify-content: center;
        }

        .phone-card .number {
            font-size: 1.8rem;
            font-weight: 700;
            color: #1d3d31;
            letter-spacing: 1.5px;
            word-break: break-word;
        }

        .phone-card .label {
            font-size: 1rem;
            text-transform: uppercase;
            color: #4f7b6b;
            font-weight: 600;
            margin-top: 6px;
        }

        /* extra action buttons */
        .cta-row {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: center;
            gap: 1rem;
            margin-top: 1.8rem;
        }

        .btn-wa, .btn-call {
            text-decoration: none;
            padding: 1rem 2rem;
            border-radius: 60px;
            font-weight: 700;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            font-size: 1.3rem;
            transition: 0.2s;
            border: 1px solid transparent;
        }

        .btn-wa {
            background: #25D366;
            color: white;
            box-shadow: 0 7px 0 #1a8a4a;
        }

        .btn-wa:hover {
            background: #20b859;
            transform: translateY(3px);
            box-shadow: 0 4px 0 #1a8a4a;
        }

        .btn-call {
            background: #3399ff;
            color: white;
            box-shadow: 0 7px 0 #1d5b9e;
        }

        .btn-call:hover {
            background: #2b87e0;
            transform: translateY(3px);
            box-shadow: 0 4px 0 #1d5b9e;
        }

        /* Kibera safi laundromat quote / always open reminder */
        .hilltop-footer {
            background: #1e3b2f;
            color: #f5eac1;
            padding: 1rem 2rem;
            text-align: center;
            border-top: 6px solid #b98c4b;
            font-size: 1.3rem;
            font-weight: 600;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.8rem;
            flex-wrap: wrap;
        }

        .hilltop-footer span {
            background: #412d12;
            padding: 0.3rem 1rem;
            border-radius: 30px;
            color: #ffd966;
            font-size: 1.5rem;
        }

        .small-note {
            background: #fffae6;
            padding: 0.8rem;
            font-size: 1.15rem;
            color: #224f40;
            border-radius: 40px;
            margin: 1rem 0 0;
            border: 1px dashed #ceb27c;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.6rem;
        }

        .small-note i {
            color: #c04343;
            font-size: 1.7rem;
        }

        /* responsive */
        @media (max-width: 520px) {
            .shop-name h1 {
                font-size: 2.2rem;
            }
            .phone-card .number {
                font-size: 1.4rem;
            }
            .photo-caption {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>
    <div class="laundry-card">
        <!-- this hero section proudly displays the photo's elements: HILLTOP LAUNDROMAT + Always Open + NO Coca‑Cola -->
        <div class="hero">
            <div class="photo-placeholder">
                <!-- visual echo of the uploaded IMG_0985.jpeg -->
                <div style="color: #fdf5da; font-size: 2.2rem; font-weight: 800; text-shadow: 4px 4px 0 #2f5a44; letter-spacing: 2px;">HILLTOP</div>
                <div style="color: white; font-size: 2.8rem; font-weight: 900; text-shadow: 3px 3px 0 #375e47; background: rgba(0, 30, 10, 0.3); border-radius: 30px; padding: 0.1rem 0.5rem; display: inline-block; margin: 8px 0;">LAUNDROMAT</div>
                <div style="color: #fad675; font-size: 1.8rem; font-weight: 600; margin: 6px 0;">⏰ Always Open</div>
            </div>
            <div class="photo-caption">
                <i class="fas fa-ban" style="color: #ea4545;"></i>
                <span style="background: #212d26; padding: 0.3rem 1.2rem; border-radius: 40px;">NO</span>
                <i class="fab fa-coca-cola" style="color: #f33;"></i>
            </div>
            <!-- explicit "NO Coca‑Cola" from the photo -->
            <div class="smoking-no">🚫 smoking</div>
        </div>

        <!-- Business identity: Kibera Safi Laundromat -->
        <div class="shop-name">
            <h1>
                <i class="fas fa-soap"></i> KIBERA SAFI <i class="fas fa-droplet"></i><br>
                <span style="font-size: 2rem;">LAUNDROMAT</span>
            </h1>
            <div class="tagline"><i class="fas fa-star"></i> safi kabisa · always fresh <i class="fas fa-star"></i></div>
        </div>

        <!-- Contacts area: both numbers clearly displayed (with photo context) -->
        <div class="contact-block">
            <div class="two-numbers">
                <!-- contact 1: 0795867025 -->
                <div class="phone-card">
                    <i class="fas fa-phone-alt"></i>
                    <div class="number">0795 867025</div>
                    <div class="label">mobile / WhatsApp</div>
                </div>
                <!-- contact 2: 0718538079 -->
                <div class="phone-card">
                    <i class="fas fa-mobile-alt"></i>
                    <div class="number">0718 538079</div>
                    <div class="label">to place your orders / call</div>
                </div>
            </div>

            <!-- call to action using both numbers (clickable) -->
            <div class="cta-row">
                <a href="https://wa.me/254795867025?text=Hello%20Kibera%20Safi%2C%20I%20need%20laundry%20service" target="_blank" class="btn-wa"><i class="fab fa-whatsapp"></i> 0795 867025</a>
                <a href="tel:+254718538079" class="btn-call"><i class="fas fa-phone"></i> 0718 538079</a>
            </div>

            <!-- small note to reflect the hilltop & coca cola message from the photo (and include the second number) -->
            <div class="small-note">
                <i class="fas fa-mountain"></i> HILLTOP vibes · NO Coca‑Cola · always open 
                <i class="fas fa-clock"></i>
            </div>
            <div style="text-align: center; margin-top: 1rem; color: #256454; font-weight: 500;">
                <i class="fas fa-tshirt"></i> drop-off & pickup · 0795 867025 / 0718 538079
            </div>
        </div>

        <!-- footer with the iconic “Always Open” & hilltop reference -->
        <div class="hilltop-footer">
            <span><i class="far fa-clock"></i> 24/7 ALWAYS OPEN</span>
            <i class="fas fa-water"></i> Kibera Safi Laundromat <i class="fas fa-cloud-sun"></i>
        </div>
    </div>

    <!-- micro note: the photo from IMG_0985.jpeg is artistically included above (hilltop / no coke) -->
    <div style="margin-top: 1.2rem; font-size: 0.9rem; color: #456b5c; background: #ebf6ef; padding: 0.7rem 2rem; border-radius: 60px; max-width: 780px; text-align: center;">
        <i class="fas fa-image"></i> “IMG_0985.jpeg” feature: KIBERA SAFI LAUNDROMAT, Always Open, CLEANLINESS WITH DIGNITY — integrated with Kibera Safi style.
    </div>
</body>
</html>
