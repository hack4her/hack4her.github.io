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
