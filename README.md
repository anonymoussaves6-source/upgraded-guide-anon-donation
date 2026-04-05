<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Anonymous Collective • Direct. Private. Impact.</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Space+Grotesk:wght@500;600;700&display=swap');
        
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            color: #e0e0e0;
            background: #0a0a0a;
        }
        
        header {
            background: linear-gradient(rgba(0,0,0,0.78), rgba(0,0,0,0.78)), 
                        url('https://drive.google.com/uc?export=view&id=1pJs8fyjLQHac167q137HZP8ncYpKeJPl') center/cover no-repeat;
            color: white;
            text-align: center;
            padding: 140px 20px 100px;
            background-position: center;
        }
        
        .logo {
            font-family: 'Space Grotesk', sans-serif;
            font-size: 2.8rem;
            font-weight: 700;
            letter-spacing: -2px;
            color: #00ff9f;
            text-shadow: 0 0 20px #00ff9f;
        }
        
        .tagline { font-size: 1.1rem; letter-spacing: 4px; opacity: 0.9; margin-bottom: 10px; }
        h1 { font-size: 3.5rem; margin-bottom: 20px; font-weight: 700; }
        .subtitle { font-size: 1.35rem; max-width: 720px; margin: 0 auto 40px; opacity: 0.95; }
        
        .donate-btn {
            background: #00ff9f;
            color: #0a0a0a;
            border: none;
            padding: 18px 50px;
            font-size: 1.35rem;
            font-weight: 700;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 0 25px rgba(0, 255, 159, 0.4);
        }
        .donate-btn:hover { transform: scale(1.05); box-shadow: 0 0 40px rgba(0, 255, 159, 0.6); }
        
        section { padding: 90px 20px; max-width: 1200px; margin: 0 auto; }
        
        .donation-section {
            background: #111;
            border-radius: 24px;
            box-shadow: 0 20px 60px rgba(0, 255, 159, 0.1);
            padding: 70px 50px;
            text-align: center;
            border: 1px solid #00ff9f22;
        }
        
        .tabs {
            display: flex; justify-content: center; margin-bottom: 50px; border-bottom: 2px solid #333;
        }
        .tab {
            padding: 16px 40px; font-size: 1.25rem; font-weight: 600; cursor: pointer; color: #aaa;
        }
        .tab.active { color: #00ff9f; border-bottom: 4px solid #00ff9f; }
        
        .amount-options {
            display: flex; justify-content: center; gap: 16px; flex-wrap: wrap; margin: 35px 0;
        }
        .amount-btn {
            background: #1a1a1a; border: 2px solid #333; color: #ddd;
            padding: 16px 32px; font-size: 1.25rem; font-weight: 600;
            border-radius: 12px; cursor: pointer; transition: all 0.3s;
        }
        .amount-btn.active, .amount-btn:hover {
            background: #00ff9f; color: #0a0a0a; border-color: #00ff9f;
        }
        
        .custom-amount {
            width: 100%; max-width: 320px; margin: 25px auto; padding: 16px;
            font-size: 1.25rem; background: #1a1a1a; border: 2px solid #333;
            border-radius: 12px; color: white; text-align: center;
        }
        
        .btc-equivalent {
            font-size: 1.15rem; color: #00ff9f; margin: 20px 0; font-weight: 600;
            background: #1a1a1a; padding: 14px; border-radius: 10px;
        }
        
        .gift-card-btn {
            background: #00ff9f; color: #0a0a0a; border: none;
            padding: 18px 60px; font-size: 1.4rem; font-weight: 700;
            border-radius: 50px; cursor: pointer; margin: 15px auto;
            display: block; width: fit-content;
            text-decoration: none;
        }
        .gift-card-btn:hover { transform: scale(1.05); }
        
        .fiat-section, .bitcoin-section {
            max-width: 520px; margin: 40px auto; padding: 35px;
            background: #1a1a1a; border-radius: 20px; border: 2px solid #00ff9f33;
        }
        
        .qr-container {
            margin: 25px auto; padding: 20px; background: white;
            border-radius: 16px; display: inline-block;
        }
        
        .btc-address {
            font-family: monospace; font-size: 1.05rem; word-break: break-all;
            background: #222; padding: 16px; border-radius: 10px;
            border: 1px solid #00ff9f44; color: #00ff9f; margin: 20px 0;
        }
        
        .copy-btn {
            background: #00ff9f; color: #0a0a0a; border: none;
            padding: 10px 24px; border-radius: 8px; cursor: pointer; font-weight: 600;
        }
        
        .privacy-note { font-size: 1rem; color: #888; margin-top: 30px; font-style: italic; }
        
        /* Optimized Confirmation Page */
        .confirmation {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.96);
            z-index: 1000;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }
        
        .confirmation-content {
            max-width: 520px;
            background: #111;
            border: 3px solid #00ff9f;
            border-radius: 24px;
            padding: 60px 40px;
            box-shadow: 0 0 60px rgba(0, 255, 159, 0.25);
            text-align: center;
        }
        
        .success-icon {
            font-size: 4.5rem;
            margin-bottom: 20px;
            animation: pop 0.6s ease;
        }
        
        @keyframes pop {
            0% { transform: scale(0.3); }
            50% { transform: scale(1.15); }
            100% { transform: scale(1); }
        }
        
        .confirmation h2 {
            color: #00ff9f;
            font-size: 2.6rem;
            margin-bottom: 12px;
        }
        
        .confirmation p {
            font-size: 1.22rem;
            line-height: 1.5;
            margin: 18px 0;
            opacity: 0.95;
        }
        
        .return-btn {
            background: #00ff9f;
            color: #0a0a0a;
            border: none;
            padding: 16px 55px;
            font-size: 1.15rem;
            font-weight: 700;
            border-radius: 50px;
            cursor: pointer;
            margin-top: 25px;
            transition: all 0.3s;
        }
        
        .return-btn:hover {
            transform: scale(1.08);
            box-shadow: 0 0 30px rgba(0, 255, 159, 0.5);
        }
        
        footer {
            background: #000; color: #666; text-align: center;
            padding: 70px 20px; font-size: 0.95rem;
        }
        .we-are { color: #00ff9f; font-family: 'Space Grotesk', sans-serif; letter-spacing: 3px; }
    </style>
</head>
<body>
    <header>
        <div class="tagline">WE ARE ANONYMOUS</div>
        <div class="logo">ANONYMOUS COLLECTIVE</div>
        <h1>Direct. Private.<br>Real Impact.</h1>
        <p class="subtitle">No names. No middlemen.<br>Choose in USD • Send in Bitcoin • Full anonymity.</p>
        <button class="donate-btn" onclick="document.getElementById('donation-section').scrollIntoView({ behavior: 'smooth' })">
            Donate Now — Stay Anonymous
        </button>
    </header>

    <section id="donation-section" class="donation-section">
        <h2 style="font-size: 2.8rem; margin-bottom: 15px; color: #00ff9f;">Support the Collective</h2>
        <p style="font-size: 1.25rem; max-width: 600px; margin: 0 auto 40px;">Send an Apple, Steam, or Razer Gold gift card or donate via Bitcoin.</p>
        
        <div class="tabs">
            <div class="tab active" onclick="switchTab(0)" id="tab-fiat">Gift Card Donation</div>
            <div class="tab" onclick="switchTab(1)" id="tab-btc">Bitcoin (Choose in USD • Send in Bitcoin)</div>
        </div>
        
        <!-- Gift Card Tab -->
        <div id="fiat-tab">
            <div class="fiat-section">
                <h3 style="margin-bottom: 25px; color: #00ff9f;">Donate with Gift Card</h3>
                <p style="margin-bottom: 20px;">We currently accept only <strong>Apple Gift Cards</strong>, <strong>Steam Gift Cards</strong>, and <strong>Razer Gold Gift Cards</strong>.</p>
                
                <div style="background:#222; padding:20px; border-radius:12px; margin:25px 0; font-size:1.1rem;">
                    <strong>Send gift card code to:</strong><br>
                    <span style="color:#00ff9f;">anonymoussaves6@gmail.com</span>
                </div>
                
                <a href="https://www.apple.com/gift-cards/" target="_blank" class="gift-card-btn">🍎 Buy Apple Gift Card</a>
                <a href="https://store.steampowered.com/digitalgiftcards/" target="_blank" class="gift-card-btn" style="background:#1b2838; color:white;">🛠️ Buy Steam Gift Card</a>
                <a href="https://gold.razer.com/" target="_blank" class="gift-card-btn">⚡ Buy Razer Gold Gift Card</a>
                
                <button onclick="showConfirmation('Gift Card', '')" class="gift-card-btn" style="background:#ffcc00; color:#0a0a0a; margin-top:15px;">
                    ✅ I've Sent the Gift Card
                </button>
                
                <div class="privacy-note">Completely anonymous. No personal data required.</div>
            </div>
        </div>
        
        <!-- Bitcoin Tab -->
        <div id="btc-tab" style="display: none;">
            <div class="bitcoin-section">
                <h3 style="margin-bottom: 25px; color: #00ff9f;">Choose in USD • Send in Bitcoin</h3>
                
                <div class="amount-options">
                    <button class="amount-btn active" data-usd="25" onclick="updateBTCAmount(this)">$25</button>
                    <button class="amount-btn" data-usd="50" onclick="updateBTCAmount(this)">$50</button>
                    <button class="amount-btn" data-usd="100" onclick="updateBTCAmount(this)">$100</button>
                    <button class="amount-btn" data-usd="250" onclick="updateBTCAmount(this)">$250</button>
                    <button class="amount-btn" data-usd="500" onclick="updateBTCAmount(this)">$500</button>
                </div>
                
                <input type="number" id="custom-usd" class="custom-amount" placeholder="Other USD amount" min="1" oninput="updateCustomBTCAmount()">
                
                <div id="btc-equivalent" class="btc-equivalent">
                    $100 ≈ <strong>0.00149 BTC</strong> (at \~$67,000 / BTC)
                </div>
                
                <p style="color:#ffcc00; font-size:0.95rem; margin:15px 0;">
                    ⚠️ Bitcoin price fluctuates rapidly. The BTC amount shown is approximate. 
                    Always check the latest price in your wallet before sending.
                </p>
                
                <div id="btc-address" class="btc-address">
                    1KWKkr72hTXYXTEcwr1mDUHGGuxGHuR2KS
                </div>
                
                <button class="copy-btn" onclick="copyAddress()">Copy Address</button>
                
                <div class="qr-container">
                    <img id="btc-qr" src="" alt="Bitcoin QR Code" style="width: 240px; height: 240px;">
                </div>
                
                <button onclick="showConfirmation('Bitcoin', document.getElementById('btc-equivalent').textContent)" class="gift-card-btn" style="margin-top:20px;">
                    ✅ I've Sent the Bitcoin
                </button>
                
                <p class="privacy-note" style="margin-top: 25px;">
                    Send the exact BTC amount shown to the address above.<br>
                    Your identity remains completely private.
                </p>
            </div>
        </div>
    </section>

    <!-- Optimized Confirmation Page -->
    <div id="confirmation-page" class="confirmation">
        <div class="confirmation-content">
            <div class="success-icon">✅</div>
            <h2>Thank You</h2>
            <p id="confirmation-message" style="font-size: 1.28rem; line-height: 1.6;"></p>
            <p style="color: #00ff9f; margin: 30px 0; font-size: 1.15rem;">
                Your donation was received anonymously.<br>
                No tracking. No receipts. Pure impact.
            </p>
            <button onclick="hideConfirmation()" class="return-btn">
                Make Another Donation
            </button>
        </div>
    </div>

    <section style="background: #111; text-align: center;">
        <h2 style="font-size: 2.2rem; margin-bottom: 50px; color: #00ff9f;">Real Impact, Anonymous Stories</h2>
        <div style="display: flex; justify-content: center; gap: 30px; flex-wrap: wrap; max-width: 1000px; margin: 0 auto;">
            <div style="background: #1a1a1a; padding: 35px; border-radius: 16px; max-width: 320px; border: 1px solid #00ff9f22;">
                <p style="font-style: italic;">"One anonymous gift covered emergency medical costs for an entire family. No questions asked."</p>
                <p style="margin-top: 25px; opacity: 0.7;">— Recipient in need</p>
            </div>
            <div style="background: #1a1a1a; padding: 35px; border-radius: 16px; max-width: 320px; border: 1px solid #00ff9f22;">
                <p style="font-style: italic;">"The collective funded supplies that reached communities ignored by traditional systems."</p>
                <p style="margin-top: 25px; opacity: 0.7;">— Field coordinator</p>
            </div>
        </div>
    </section>

    <footer>
        <p class="we-are">WE ARE ANONYMOUS • WE ARE LEGION • WE DO NOT FORGET • WE DO NOT FORGIVE</p>
        <p style="margin-top: 30px; opacity: 0.6;">Direct action through decentralized giving.<br>Expect us.</p>
        <p style="margin-top: 40px; font-size: 0.85rem;">© Anonymous Collective • Built for privacy and impact</p>
    </footer>

    <script>
        const BTC_PRICE_USD = 67000;
        
        function switchTab(tab) {
            document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
            if (tab === 0) {
                document.getElementById('tab-fiat').classList.add('active');
                document.getElementById('fiat-tab').style.display = 'block';
                document.getElementById('btc-tab').style.display = 'none';
            } else {
                document.getElementById('tab-btc').classList.add('active');
                document.getElementById('fiat-tab').style.display = 'none';
                document.getElementById('btc-tab').style.display = 'block';
                updateBTCAmount(document.querySelector('#btc-tab .amount-btn.active'));
            }
        }
        
        const btcAddress = "1KWKkr72hTXYXTEcwr1mDUHGGuxGHuR2KS";
        
        function usdToBtc(usd) {
            return (usd / BTC_PRICE_USD).toFixed(6);
        }
        
        function updateBTCAmount(btn) {
            document.querySelectorAll('#btc-tab .amount-btn').forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            document.getElementById('custom-usd').value = '';
            const usd = parseFloat(btn.dataset.usd);
            const btc = usdToBtc(usd);
            document.getElementById('btc-equivalent').innerHTML = 
                `\[ {usd} ≈ <strong>${btc} BTC</strong> (at \~ \]{BTC_PRICE_USD.toLocaleString()} / BTC)`;
            generateQR(btcAddress, btc);
        }
        
        function updateCustomBTCAmount() {
            document.querySelectorAll('#btc-tab .amount-btn').forEach(b => b.classList.remove('active'));
            const usd = parseFloat(document.getElementById('custom-usd').value);
            if (!usd || usd <= 0) return;
            const btc = usdToBtc(usd);
            document.getElementById('btc-equivalent').innerHTML = 
                `\[ {usd} ≈ <strong>${btc} BTC</strong> (at \~ \]{BTC_PRICE_USD.toLocaleString()} / BTC)`;
            generateQR(btcAddress, btc);
        }
        
        function generateQR(address, btcAmount) {
            const qrText = btcAmount ? `bitcoin:\( {address}?amount= \){btcAmount}` : address;
            const qrUrl = `https://api.qrserver.com/v1/create-qr-code/?size=300x300&data=${encodeURIComponent(qrText)}`;
            document.getElementById('btc-qr').src = qrUrl;
        }
        
        function copyAddress() {
            navigator.clipboard.writeText(btcAddress).then(() => {
                const btn = event.target;
                const orig = btn.textContent;
                btn.textContent = "Copied!";
                setTimeout(() => btn.textContent = orig, 1800);
            });
        }
        
        function showConfirmation(type, details = '') {
            let message = '';
            if (type === 'Gift Card') {
                message = 'Your gift card has been received.<br>Thank you for supporting the Collective anonymously.';
            } else {
                message = `Your Bitcoin donation<br>(${details}) has been received.<br>Thank you for your anonymous contribution.`;
            }
            document.getElementById('confirmation-message').innerHTML = message;
            document.getElementById('confirmation-page').style.display = 'flex';
        }
        
        function hideConfirmation() {
            document.getElementById('confirmation-page').style.display = 'none';
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }
    </script>
</body>
</html>
