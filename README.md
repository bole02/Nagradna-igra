<!DOCTYPE html><html lang="sr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nagradni Izazov</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; padding: 20px; }
        .container { max-width: 400px; margin: auto; }
        input, button { width: 100%; padding: 10px; margin: 5px 0; }
        #countdown { font-size: 20px; margin: 20px 0; }
    </style>
</head>
<body>
    <div class="container">
        <h1>Osvoji 1000€</h1>
        <p>Uplati 2€ i učestvuj u izvlačenju 22. juna!</p>
        <form id="challengeForm">
            <input type="text" id="name" placeholder="Ime" required>
            <input type="email" id="email" placeholder="Email" required>
            <input type="tel" id="phone" placeholder="Broj telefona" required>
            <button type="button" onclick="payWithPayPal()">Uplati 2€</button>
        </form>
        <div id="countdown"></div>
    </div><script>
    function payWithPayPal() {
        alert("Preusmeravanje na PayPal...");
        window.location.href = "https://www.paypal.com"; 
    }
    
    function countdown() {
        let eventDate = new Date("2025-06-22").getTime();
        setInterval(function() {
            let now = new Date().getTime();
            let timeLeft = eventDate - now;
            let days = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
            let hours = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            let minutes = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
            let seconds = Math.floor((timeLeft % (1000 * 60)) / 1000);
            document.getElementById("countdown").innerText = `Izvlačenje za: ${days}d ${hours}h ${minutes}m ${seconds}s`;
        }, 1000);
    }
    countdown();
</script>

</body>
</html>
