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
      background:  #E7C6FF;
    }

  .schedule-section {
    background: linear-gradient(160deg, #4ecdc4 0%, #45b7b0 60%, #3aa8a1 100%);
    padding: 3rem 1.5rem 4rem;
    min-height: 100vh;
    border-radius: 24px;        /* ← add this */
    margin: 1.5rem;             /* ← optional: adds space around it */
  }

    h1 {
      text-align: center;
      color: #2d2d2d;
      font-size: 2.2rem;
      font-weight: 800;
      margin-bottom: 2rem;
      letter-spacing: 0.5px;
    }

    .day-tabs {
      display: flex;
      justify-content: center;
      gap: 0;
      background: rgba(255,255,255,0.25);
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
      color: rgba(255,255,255,0.85);
      border: none;
      background: transparent;
      transition: background 0.2s, color 0.2s;
    }

    .day-tab.active {
      background: #f9a8d4;
      color: #7c3aed;
    }

    .day-tab:hover:not(.active) {
      background: rgba(255,255,255,0.15);
      color: #fff;
    }

    .day-panel { display: none; }
    .day-panel.active { display: block; }

    .day-header {
      text-align: center;
      margin-bottom: 1.5rem;
    }

    .day-header h2 {
      color: ##2d2d2d;
      font-size: 1.5rem;
      font-weight: 800;
    }

    .day-header p {
      color: rgba(255,255,255,0.8);
      font-size: 0.95rem;
      margin-top: 4px;
    }

    .divider {
      border: none;
      border-top: 1px solid rgba(255,255,255,0.4);
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
      background: rgba(255,255,255,0.18);
      border-radius: 16px;
      padding: 1rem 1.5rem;
      display: flex;
      align-items: center;
      gap: 1.5rem;
      backdrop-filter: blur(4px);
      transition: background 0.2s;
    }

    .event-card:hover {
      background: rgba(255,255,255,0.28);
    }

    .event-time {
      color: rgba(255,255,255,0.9);
      font-size: 0.9rem;
      font-weight: 600;
      white-space: nowrap;
      min-width: 110px;
    }

    .event-info {
      flex: 1;
    }

    .event-title {
      color: #2d2d2d;
      font-size: 1rem;
      font-weight: 800;
    }

    .event-location {
      color: rgba(255,255,255,0.75);
      font-size: 0.875rem;
      font-style: italic;
      margin-top: 2px;
    }

    .event-badge {
      background: rgba(255,255,255,0.9);
      color: #0d9488;
      border-radius: 50px;
      padding: 4px 16px;
      font-size: 0.85rem;
      font-weight: 700;
      white-space: nowrap;
    }

    .event-badge.pink {
      background: #f9a8d4;
      color: #9d174d;
    }

    .event-badge.yellow {
      background: #fde68a;
      color: #92400e;
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
      <p>Workshops &amp; Networking</p>
    </div>
    <hr class="divider" />
    <div class="schedule-list">

      <!-- Each event follows this pattern:
           - event-time: the time slot
           - event-title: name of the event
           - event-location: where it takes place
           - event-badge (optional): label pill. Add class "pink" or "yellow" for color variants.
             Remove the <span class="event-badge"> line entirely if no badge needed. -->

      <div class="event-card">
        <span class="event-time">13:45 – 14:00</span>
        <div class="event-info">
          <div class="event-title">Arrival &amp; Check-In</div>
          <div class="event-location">Vrije Universiteit Amsterdam – NU Building Ground Floor</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">14:00 – 14:15</span>
        <div class="event-info">
          <div class="event-title">Introduction</div>
          <div class="event-location">NU-Theatre 1</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">14:15 – 15:00</span>
        <div class="event-info">
          <div class="event-title">A word from our sponsors!</div>
          <div class="event-location">NU-Theatre 1</div>
        </div>
        <span class="event-badge pink">Sponsor</span>
      </div>

      <div class="event-card">
        <span class="event-time">15:00 – 15:30</span>
        <div class="event-info">
          <div class="event-title">Keynote</div>
          <div class="event-location">NU-Theatre 1</div>
        </div>
        <span class="event-badge">Keynote</span>
      </div>

      <div class="event-card">
        <span class="event-time">15:30 – 17:00</span>
        <div class="event-info">
          <div class="event-title">Workshops Session 1</div>
          <div class="event-location">Various rooms</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">17:00 – 18:30</span>
        <div class="event-info">
          <div class="event-title">Networking &amp; Dinner</div>
          <div class="event-location">NU Building Foyer</div>
        </div>
        <span class="event-badge yellow">Food</span>
      </div>

    </div>
  </div>

  <!-- ===================== SATURDAY ===================== -->
  <div id="saturday" class="day-panel">
    <div class="day-header">
      <h2>Saturday, June 14</h2>
      <p>Hacking Begins</p>
    </div>
    <hr class="divider" />
    <div class="schedule-list">

      <div class="event-card">
        <span class="event-time">09:00 – 09:30</span>
        <div class="event-info">
          <div class="event-title">Hacking Kick-Off</div>
          <div class="event-location">NU-Theatre 1</div>
        </div>
        <span class="event-badge">Main Stage</span>
      </div>

      <div class="event-card">
        <span class="event-time">09:30 – 12:30</span>
        <div class="event-info">
          <div class="event-title">Hacking + Morning Workshops</div>
          <div class="event-location">Various rooms</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">12:30 – 13:30</span>
        <div class="event-info">
          <div class="event-title">Lunch Break</div>
          <div class="event-location">NU Building Foyer</div>
        </div>
        <span class="event-badge yellow">Food</span>
      </div>

      <div class="event-card">
        <span class="event-time">13:30 – 18:00</span>
        <div class="event-info">
          <div class="event-title">Hacking + Afternoon Workshops</div>
          <div class="event-location">Various rooms</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">18:00 – 19:00</span>
        <div class="event-info">
          <div class="event-title">Dinner</div>
          <div class="event-location">NU Building Foyer</div>
        </div>
        <span class="event-badge yellow">Food</span>
      </div>

    </div>
  </div>

  <!-- ===================== SUNDAY ===================== -->
  <div id="sunday" class="day-panel">
    <div class="day-header">
      <h2>Sunday, June 15</h2>
      <p>Submissions &amp; Awards</p>
    </div>
    <hr class="divider" />
    <div class="schedule-list">

      <div class="event-card">
        <span class="event-time">09:00 – 11:00</span>
        <div class="event-info">
          <div class="event-title">Final Hacking Sprint</div>
          <div class="event-location">Hacking Room</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">11:00 – 11:30</span>
        <div class="event-info">
          <div class="event-title">Submissions Deadline</div>
          <div class="event-location">Online</div>
        </div>
        <span class="event-badge pink">Deadline</span>
      </div>

      <div class="event-card">
        <span class="event-time">11:30 – 13:00</span>
        <div class="event-info">
          <div class="event-title">Project Presentations</div>
          <div class="event-location">NU-Theatre 1</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">13:00 – 13:30</span>
        <div class="event-info">
          <div class="event-title">Judging &amp; Deliberation</div>
          <div class="event-location">NU-Theatre 1</div>
        </div>
      </div>

      <div class="event-card">
        <span class="event-time">13:30 – 14:30</span>
        <div class="event-info">
          <div class="event-title">Awards Ceremony &amp; Closing</div>
          <div class="event-location">NU-Theatre 1</div>
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
