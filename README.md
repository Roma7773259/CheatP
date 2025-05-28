<!DOCTYPE html>
<html>
<head>
  <title>Перегляд</title>
  <script>
    async function checkStatus() {
      try {
        const response = await fetch("https://docs.google.com/document/d/1KGYEXJ7CZQr9Owk2E3YJVXYnl3SPC40gmfIQPCtZjMU/export?format=txt");
        const text = await response.text();
        const img = document.getElementById("image");

        if (text.trim().toLowerCase() === "show") {
          img.style.display = "block";
        } else {
          img.style.display = "none";
        }
      } catch (e) {
        console.error("Помилка при зчитуванні:", e);
      }
    }

    setInterval(checkStatus, 3000); // перевірка кожні 3 секунди
  </script>
</head>
<body onload="checkStatus()">
  <h1>Перегляд</h1>
  <img id="image" src="https://mobilaser.kz/wp-content/uploads/2022/07/hacked.jpg" style="display:none; max-width: 100%; height: auto;" />
</body>
</html>
