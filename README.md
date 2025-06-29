# <!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Удостоверение личности</title>
  <style>
    body {
      font-family: Arial;
      background: #f3f3f3;
      padding: 20px;
    }
    .container {
      max-width: 400px;
      margin: auto;
      background: white;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    h2 {
      text-align: center;
      color: #333;
    }
    label {
      display: block;
      margin: 10px 0 5px;
    }
    input, button {
      width: 100%;
      padding: 10px;
      margin-bottom: 15px;
    }
    .tabs {
      display: flex;
      justify-content: space-around;
      margin-bottom: 20px;
    }
    .tabs div {
      padding: 10px;
      cursor: pointer;
      border-bottom: 2px solid transparent;
    }
    .tabs .active {
      border-bottom: 2px solid #000;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>Удостоверение личности</h2>
    <div class="tabs">
      <div class="tab active" onclick="showTab('doc')">Документ</div>
      <div class="tab" onclick="showTab('info')">Реквизиты</div>
    </div>
    <div id="docTab">
      <label>Загрузите документ:</label>
      <input type="file" />
    </div>
    <div id="infoTab" style="display:none;">
      <label>ФИО:</label>
      <input type="text" placeholder="Иванов Иван" />
      <label>ИИН:</label>
      <input type="text" placeholder="000000000000" />
      <label>Номер удостоверения:</label>
      <input type="text" placeholder="123456789" />
      <label>Дата выдачи:</label>
      <input type="date" />
    </div>
    <button onclick="alert('Документ предъявлен')">Предъявить документ</button>
    <button onclick="alert('Документ отправлен')">Отправить документ</button>
  </div>

  <script>
    function showTab(tab) {
      document.getElementById('docTab').style.display = (tab === 'doc') ? 'block' : 'none';
      document.getElementById('infoTab').style.display = (tab === 'info') ? 'block' : 'none';
      document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
      document.querySelectorAll('.tab').forEach(t => {
        if (t.textContent.toLowerCase().includes(tab)) t.classList.add('active');
      });
    }
  </script>
</body>
</html>
