<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Event Schedule – Hack4Her</title>
  <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      font-family: 'Nunito', sans-serif;
      background: #f9f9f9;
    }

    .schedule-section {
      background: #E7C6FF;
      padding: 3rem 1.5rem 4rem;
      min-height: 100vh;
      border-radius: 24px;
      margin: 1.5rem;
    }

    h1 {
      text-align: center;
      color: #000;
      font-size: 2.2rem;
      font-weight: 800;
      margin-bottom: 2rem;
      letter-spacing: -0.5px;
    }

    .day-tabs {
      display: flex;
      justify-content: center;
      gap: 0;
      background: rgba(0,0,0,0.08);
      border-radius: 50px;
      padding: 5px;
      max-width: 420px;
      margin: 0 auto 2.5rem;
    }

    .day-tab {
      flex: 1;
      text-align: center;
      padding: 10px 20px;
      border-radius: 50px;
      font-size: 1rem;
      font-weight: 700;
      cursor: pointer;
      color: rgba(0,0,0,0.6);
      border: none;
      background: transparent;
      transition: background 0.2s, color 0.2s;
    }

    .day-tab.active {
      background: #faf9f6;
      color: #000;
    }

    .day-tab:hover:not(.active) {
      background: rgba(0,0,0,0.08);
      color: #000;
    }

    .day-panel { display: none; }
    .day-panel.active { display: block; }

    .day-header {
      text-align: center;
      margin-bottom: 1.5rem;
    }

    .day-header h2 {
      color: #000;
      font-size: 1.5rem;
      font-weight: 800;
    }

    .day-header p {
      color: rgba(0,0,0,0.6);
      font-size: 0.95rem;
      margin-top: 4px;
    }

    .divider {
      border: none;
      border-top: 1px solid rgba(0,0,0,0.15);
      margin: 1rem 0 1.5rem;
    }

    .schedule-list {
      display: flex;
      flex-direction: column;
      gap: 12px;
      max-width: 860px;
      margin: 0 auto;
    }

    .event-card {
      background: #faf9f6;
      border-radius: 16px;
      padding: 1rem 1.5rem;
      display: flex;
      align-items: center;
      gap: 1.5rem;
      transition: background 0.2s;
    }

    .event-card:hover {
      background: #f0eef9;
    }

    .event-time {
      color: rgba(0,0,0,0.55);
      font-size: 0.9rem;
      font-weight: 600;
      white-space: nowrap;
      min-width: 110px;
    }

    .event-info {
      flex: 1;
    }

    .event-title {
      color: #000;
      font-size: 1rem;
      font-weight: 800;
    }

    .event-location {
      color: rgba(0,0,0,0.55);
      font-size: 0.875rem;
      font-style: italic;
      margin-top: 2px;
    }

    .event-badge {
      background: #E7C6FF;
      color: #000;
      border-radius: 50px;
      padding: 4px 16px;
      font-size: 0.85rem;
      font-weight: 700;
      white-space: nowrap;
    }

    .event-badge.pink {
      background: #f9a8d4;
      color: #000;
    }

    .event-badge.yellow {
      background: #fde68a;
      color: #000;
    }

    @media (max-width: 600px) {
      .event-card { flex-direction: column; align-items: flex-start; gap: 6px; }
      .event-time { min-width: unset; }
      h1 { font-size: 1.7rem; }
    }
  </style>
</head>
<body>

<section class="schedule-section">
  <h1>Event Schedule</h1>

  <div class="day-tabs">
    <button class="day-tab active" onclick="showDay('friday', this)">Friday</button>
    <button class="day-tab" onclick="showDay('saturday', this)">Saturday</button>
    <button class="day-tab" onclick="showDay('sunday', this)">Sunday</button>
  </div>

  <!-- ===================== FRIDAY ===================== -->
  <div id="friday" class="day-panel active">
    <div class="day-header">
      <h2>Friday, June 12</h2>
      <p>Opening &amp; Networking</p>
    </div>
    <hr class="divider" />
    <div class="schedule-list">

      <div class="event-card">
        <span class="event-time">17:30 – 18:00</span>
        <div class="event-info">
          <div class="event-title">Arrival &amp; Check-In</div>
          <div class="event-location">TU/e campus – Neuron building</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">18:00 – 18:15</span>
        <div class="event-info">
          <div class="event-title">Introduction</div>
          <div class="event-location">Neuron</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">18:15 – 18.30</span>
        <div class="event-info">
          <div class="event-title">A word from our sponsors!</div>
          <div class="event-location">Neuron</div>
        </div>
        <span class="event-badge pink">Sponsor</span>
      </div>

      <div class="event-card">
        <span class="event-time">18:30 – 19.15</span>
        <div class="event-info">
          <div class="event-title">Keynote</div>
          <div class="event-location">Neuron</div>
        </div>
        <span class="event-badge">Keynote</span>
      </div>

      <div class="event-card">
        <span class="event-time">19:15 – 20.15</span>
        <div class="event-info">
          <div class="event-title">Dinner</div>
          <div class="event-location">Neuronr</div>
        </div>
        <span class="event-badge yellow">Food</span>
      </div>

    <div class="event-card">
        <span class="event-time">20:15 – 21.30</span>
        <div class="event-info">
          <div class="event-title">Networking</div>
          <div class="event-location">Neuronr</div>
        </div>
       <span class="event-badge pink">Sponsor</span>
      </div>
    </div>
  </div>

  <!-- ===================== SATURDAY ===================== -->
  <div id="saturday" class="day-panel">
    <div class="day-header">
      <h2>Saturday, June 13</h2>
      <p>Hacking Begins</p>
    </div>
    <hr class="divider" />
    <div class="schedule-list">

      <div class="event-card">
        <span class="event-time">09:00 – 09:30</span>
        <div class="event-info">
          <div class="event-title">Arrival and breakfast</div>
          <div class="event-location">Neuron</div>
        </div>
        <span class="event-badge yellow">Food</span>
      </div>

      <div class="event-card">
        <span class="event-time">09:30 – 9:45</span>
        <div class="event-info">
          <div class="event-title">Hacking Kick-Off s</div>
          <div class="event-location">Neuron</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">09:45 – 10:45</span>
        <div class="event-info">
          <div class="event-title">Challenge specific workshop</div>
          <div class="event-location">Neuron</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">11:00 – 13:30</span>
        <div class="event-info">
          <div class="event-title">Hacking</div>
          <div class="event-location">Various rooms in Neuron</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">13:30 – 14:30</span>
        <div class="event-info">
          <div class="event-title">Lunch Break</div>
          <div class="event-location">Neuron</div>
        </div>
        <span class="event-badge yellow">Food</span>
      </div>

      <div class="event-card">
        <span class="event-time">14:30 – 15:30</span>
        <div class="event-info">
          <div class="event-title">Keynote</div>
          <div class="event-location">Neuron</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">15:30 – 19:00</span>
        <div class="event-info">
          <div class="event-title">Hacking</div>
          <div class="event-location">Neuron</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">19:00 – 20:00</span>
        <div class="event-info">
          <div class="event-title">Dinner</div>
          <div class="event-location">Neuron</div>
        </div>
        <span class="event-badge yellow">Food</span>
      </div>

      <div class="event-card">
        <span class="event-time">20:00 – 21:30</span>
        <div class="event-info">
          <div class="event-title">Hacking</div>
          <div class="event-location">Neuron</div>
        </div>
      </div>

    </div>
  </div>

  <!-- ===================== SUNDAY ===================== -->
  <div id="sunday" class="day-panel">
    <div class="day-header">
      <h2>Sunday, June 14</h2>
      <p>Submissions &amp; Awards</p>
    </div>
    <hr class="divider" />
    <div class="schedule-list">

      <div class="event-card">
        <span class="event-time">09:00 – 09:30</span>
        <div class="event-info">
          <div class="event-title">Arrival &amp; Breakfast </div>
          <div class="event-location">Neuron</div>
           <span class="event-badge yellow">Food</span>
        </div>
      </div>

       <div class="event-card">
        <span class="event-time">09:30 – 9:45</span>
        <div class="event-info">
          <div class="event-title">Hacking Kick-Off s</div>
          <div class="event-location">Neuron</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">9:45 – 12:30</span>
        <div class="event-info">
          <div class="event-title">Hacking</div>
          <div class="event-location">Various rooms in Neuron</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">12:30 – 13:00</span>
        <div class="event-info">
          <div class="event-title">Submissions Deadline</div>
          <div class="event-location">Online</div>
        </div>
        <span class="event-badge pink">Deadline</span>
      </div>

      <div class="event-card">
        <span class="event-time">13:00 – 14:00</span>
        <div class="event-info">
          <div class="event-title">Lunch Break</div>
          <div class="event-location">Neuron</div>
        </div>
        <span class="event-badge yellow">Food</span>
      </div>

      <div class="event-card">
        <span class="event-time">14:00 – 15:00</span>
        <div class="event-info">
          <div class="event-title">Prepare project Presentations</div>
          <div class="event-location">Neuron</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">15:00 – 16:00</span>
        <div class="event-info">
          <div class="event-title">Judging &amp; Deliberation</div>
          <div class="event-location">Neuron</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">16:00 – 17:00</span>
        <div class="event-info">
          <div class="event-title">Awards Ceremony &amp; Closing</div>
          <div class="event-location">Neuron</div>
        </div>
        <span class="event-badge">Awards</span>
      </div>

    </div>
  </div>

</section>

<script>
  function showDay(dayId, btn) {
    document.querySelectorAll('.day-panel').forEach(p => p.classList.remove('active'));
    document.querySelectorAll('.day-tab').forEach(t => t.classList.remove('active'));
    document.getElementById(dayId).classList.add('active');
    btn.classList.add('active');
  }
</script>

</body>
</html>
