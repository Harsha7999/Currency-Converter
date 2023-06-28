# Currency-Converter
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Currency Converter</title>
  <style>
 
 body {
      background: url(Currency.jpg) center;
      font-family: Georgia, serif;
    }
    h1 {   background: 00FFFFFF;
           text-align: center;
           font-size: 50px;
           padding: 20px;
           font-weight: bold;
           margin: 0 auto;
           width: 50%;
        }
marquee {   background: 00FFFFFF;
            font-size: 20px;
            padding: 25px;
            margin: 20px auto;
            width: 100%;
    }
form {     width: 60%;
           margin: 0 auto;
           border: 1px solid #1a1a1a;
           padding: 20px;
           font-size: 18px;
           font-family: Verdana, sans-serif;
	       background: #808080; 
    }
label {
      display: inline-block;
      width: 300px;
     
    }
    input[type="number"],
    input[type="text"] {
      width: 100px;
      padding: 5px;
      border: 1px solid 00FFFFFF;
    }
    input[type="button"],
    input[type="reset"] {
      width: 90px;
      height: 35px;
      font-weight: bold;
    }
    p {
      text-align: center;
    }
</style>
  <script>
    function currencyConverter(valNum) {
      if (converter.rupees.value <= 0) {
        window.alert("Enter a value greater than 0");
      } else {
        var currency = document.getElementById("currency-select").value;
        var rates = {
          USD: 82.05, EUR: 89.38, AED: 22.33, GBP: 104.27, JPY: 0.57, CHF: 91.44, KWD: 267.85, CNY: 11.34, AUD: 54.41, NZD: 50.00, RUB: 0.96, ZAR: 4.41, MYR: 17.55, IDR: 0.55, BRL:17.04 };
       
        var rate = rates[currency] || 1;
        var convertedValue = (valNum / rate).toFixed(3);
        
        document.getElementById("converted-currency").value = convertedValue;
        document.getElementById("converted-currency-label").innerHTML = convertedValue;
      }
    }
  </script>
</head>
<body>
  <h1>Currency Converter</h1>
  <marquee>Welcome to the Online Currency Converter</marquee>
  <form name="converter">
    <label>INR (Indian Rupees):</label>
    <input type="number" name="rupees" required>
    <br><br>
    <label>Select Currency:</label>
    <select id="currency-select">
      <option value="USD">United States Dollar (USD)</option>
      <option value="EUR">Euro (EUR)</option>
	  <option value="AED">Diraham (AED)</option>
      <option value="GBP">British Pound Sterling (GBP)</option>
      <option value="JPY">Japanese Yen (JPY)</option>
      <option value="CHF">Swiss Franc (CHF)</option>
	  <option value="KWD">Dinar (KWD)</option>
	  <option value="CNY">Chinese Yuan (CNY)</option>
	  <option value="AUD">Australian Dollar (AUD)</option>
	  <option value="NZD">New Zealand (NZD)</option>
	  <option value="RUB">Russian Rubie (RUB)</option>
	  <option value="ZAR">South African Rand (ZAR)</option>
	  <option value="MYR">Malayasian Ringgit (MYR)</option>
	  <option value="IDR">Indonesian Rupiah (IDR)</option>
	  <option value="BRL">Brazilian Real (BRL)</option>
    </select>
    <br><br>
    <label>Converted Currency:</label>
    <input id="converted-currency" type="text" readonly>
    <br><br>
    <input type="button" value="Convert" onclick="currencyConverter(converter.rupees.value)">
    <input type="reset" value="Reset Form">
    <p>You can press the Reset button to reset the form</p>
  </form>
</body>
</html>
