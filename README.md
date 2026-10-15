
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>SkyBook - Flight Booking</title>
  <style>
    * { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #eef4ff;
      color: #172554;
    }
    header {
      background: #123b82;
      color: white;
      padding: 22px 8%;
      font-size: 25px;
      font-weight: bold;
    }
    main {
      max-width: 850px;
      margin: 55px auto;
      padding: 20px;
    }
    .panel {
      background: white;
      padding: 28px;
      border-radius: 18px;
      box-shadow: 0 8px 30px #1e3a8a15;
    }
    .fields {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 16px;
    }
    label { font-size: 14px; font-weight: bold; }
    input {
      display: block;
      width: 100%;
      padding: 13px;
      margin-top: 8px;
      border: 1px solid #cbd5e1;
      border-radius: 8px;
    }
    button {
      margin-top: 22px;
      width: 100%;
      padding: 15px;
      background: #2563eb;
      color: white;
      border: 0;
      border-radius: 9px;
      font-size: 16px;
      cursor: pointer;
    }
    #results { margin-top: 22px; }
    .flight {
      padding: 16px;
      margin-top: 12px;
      border: 1px solid #dbeafe;
      border-radius: 10px;
    }
    @media(max-width: 520px) {
      .fields { grid-template-columns: 1fr; }
      main { margin-top: 25px; }
    }
  </style>
</head>
<body>
  <header>✈ SkyBook</header>
  <main>
    <h1>Find your next flight</h1>
    <p>Search flights for your next adventure.</p>
    <div class="panel">
      <form id="searchForm">
        <div class="fields">
          <label>From
            <input id="from" placeholder="e.g. Delhi" required>
          </label>
          <label>To
            <input id="to" placeholder="e.g. Mumbai" required>
          </label>
          <label>Departure date
            <input id="date" type="date" required>
          </label>
          <label>Passengers
            <input id="passengers" type="number"
              min="1" max="9" value="1" required>
          </label>
        </div>
        <button type="submit">Search Flights</button>
      </form>
      <div id="results" aria-live="polite"></div>
    </div>
  </main>
  <script>
    const date = document.getElementById("date");
    date.min = new Date().toLocaleDateString("en-CA");

    document.getElementById("searchForm").addEventListener("submit", e => {
      e.preventDefault();
      const from = document.getElementById("from").value.trim();
      const to = document.getElementById("to").value.trim();
      const travelDate = date.value;
      const passengers = document.getElementById("passengers").value;

      if (from.toLowerCase() === to.toLowerCase()) {
        alert("From aur To alag cities honi chahiye.");
        return;
      }

      document.getElementById("results").innerHTML = `
        <h2>Demo Search Results</h2>
        <div class="flight">
          <strong>${escapeText(from)} → ${escapeText(to)}</strong>
          <p>Date: ${travelDate}</p>
          <p>Passengers: ${passengers}</p>
          <p>Sample flight — live flight data connected nahi hai.</p>
        </div>`;
    });

    function escapeText(value) {
      return value.replace(/[&<>"']/g, char => ({
        "&": "&amp;", "<": "&lt;", ">": "&gt;",
        '"': "&quot;", "'": "&#39;"
      })[char]);
    }
  </script>
</body>
</html>
