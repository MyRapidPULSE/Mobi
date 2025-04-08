# Mobi
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Open App</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 0;
            padding: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background-color: #f9f9f9;
        }

        #openApp {
            background-color: #007BFF;
            color: #ffffff;
            font-size: 16px;
            font-weight: bold;
            border: none;
            border-radius: 8px;
            padding: 12px 20px;
            cursor: pointer;
            box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        #openApp:hover {
            background-color: #0056b3;
            box-shadow: 0px 6px 8px rgba(0, 0, 0, 0.15);
        }

        #openApp:active {
            background-color: #00408f;
            box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.2);
            transform: scale(0.98);
        }

        #openApp:focus {
            outline: none;
        }
    </style>
</head>
<body>
    <button id="openApp">Open My App</button>

    <script>
        document.getElementById("openApp").addEventListener("click", function () {
            const userAgent = navigator.userAgent || navigator.vendor || window.opera;

            if (/android/i.test(userAgent)) {
                // Android logic
                const intentUrl = "intent://universallink.willermobi.com#Intent;scheme=https;package=jp.co.willer.maasapp;S.browser_fallback_url=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Djp.co.willer.maasapp%26pcampaignid%3Dweb_share;end";
                window.location = intentUrl;
            } else if (/iPad|iPhone|iPod/.test(userAgent) && !window.MSStream) {
                // iOS logic
                const universalLink = "https://universallink.willermobi.com/install_app.html";
                window.location.href = universalLink;
            } else {
                alert("Your device is not supported.");
            }
        });
    </script>
</body>
</html>
