<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Myxamet Shop</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://fonts.googleapis.com/css2?family=Russo+One&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Russo One', sans-serif;
      background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
      background-size: 400% 400%;
      animation: gradientBG 15s ease infinite;
      color: white;
    }

    @keyframes gradientBG {
      0% {background-position: 0% 50%;}
      50% {background-position: 100% 50%;}
      100% {background-position: 0% 50%;}
    }

    .neon-box {
      border: 2px solid #39ff14;
      box-shadow: 0 0 10px #39ff14, 0 0 20px #39ff14;
    }

    .neon-text {
      color: #39ff14;
      text-shadow: 0 0 5px #39ff14, 0 0 10px #39ff14;
    }
  </style>
</head>
<body>
  <header class="p-6 text-center">
    <h1 class="text-4xl neon-text">Myxamet Shop</h1>
  </header>

  <section class="max-w-6xl mx-auto p-4 grid grid-cols-1 md:grid-cols-3 gap-6">
    <div onclick="openModal('Алмазы')" class="cursor-pointer bg-black neon-box rounded-xl p-6 text-center">
      <h2 class="text-2xl mb-2">Алмазы</h2>
      <p>Пополнение до 50,000 алмазов</p>
      <button class="mt-4 px-6 py-2 bg-green-500 hover:bg-green-400 text-black rounded">Купить</button>
    </div>

    <div onclick="openModal('Ваучеры')" class="cursor-pointer bg-black neon-box rounded-xl p-6 text-center">
      <h2 class="text-2xl mb-2">Ваучеры</h2>
      <p>Элитный пропуск и эксклюзив</p>
      <button class="mt-4 px-6 py-2 bg-green-500 hover:bg-green-400 text-black rounded">Купить</button>
    </div>

    <div onclick="openModal('Прокачка')" class="cursor-pointer bg-black neon-box rounded-xl p-6 text-center">
      <h2 class="text-2xl mb-2">Прокачка</h2>
      <p>Помощь с ранговыми играми</p>
      <button class="mt-4 px-6 py-2 bg-green-500 hover:bg-green-400 text-black rounded">Купить</button>
    </div>
  </section>

  <section class="max-w-3xl mx-auto mt-12 p-4 bg-black neon-box rounded-xl">
    <h3 class="text-3xl neon-text mb-4">Поддерживаемые способы оплаты (СНГ)</h3>
    <ul class="list-disc list-inside text-lg">
      <li>Банковская карта (Visa, Mastercard, МИР)</li>
      <li>СБП (Система Быстрых Платежей)</li>
      <li>QIWI</li>
      <li>ЮMoney</li>
      <li>Kaspi.kz (Казахстан)</li>
      <li>O!Деньги / Элсом (Кыргызстан)</li>
      <li>Crypto USDT/BTC</li>
    </ul>
  </section>

  <section class="max-w-3xl mx-auto mt-12 p-4 bg-black neon-box rounded-xl">
    <h3 class="text-3xl neon-text mb-4">Отзывы покупателей</h3>
    <p class="text-lg">⭐️⭐️⭐️⭐️⭐️ Всё быстро, алмазы пришли за 5 минут! — <em>Игрок123</em></p>
    <p class="text-lg mt-2">⭐️⭐️⭐️⭐️ Работает! Брал ваучеры — всё чётко. — <em>FF_PRO</em></p>
    <p class="text-lg mt-2">⭐️⭐️⭐️⭐️⭐️ Прокачали ранг за вечер, спасибо 🙏 — <em>LEGEND_KG</em></p>
  </section>

  <section class="max-w-3xl mx-auto mt-12 p-4 bg-black neon-box rounded-xl text-center">
    <h3 class="text-3xl neon-text mb-2">Контакты</h3>
    <p class="text-lg">Telegram: <a href="https://t.me/tologonov_m" class="text-green-400">@tologonov_m</a></p>
    <p class="text-lg">Email: <a href="mailto:fasterff2021@gmail.com" class="text-green-400">fasterff2021@gmail.com</a></p>
  </section>

  <!-- Модальное окно -->
  <div id="modal" class="fixed inset-0 bg-black bg-opacity-80 flex items-center justify-center hidden">
    <div class="bg-gray-900 p-6 rounded-xl max-w-md w-full border border-green-400">
      <h2 class="text-xl mb-4 neon-text">Оформление заказа</h2>
      <form action="https://formspree.io/f/meokqodv" method="POST" class="space-y-4">
        <input type="hidden" id="productField" name="Продукт" value="">
        <label>ID аккаунта Free Fire:</label>
        <input name="ID аккаунта" required type="text" class="w-full p-2 rounded bg-gray-700 text-white" placeholder="123456789" />
        
        <label>Способ оплаты:</label>
        <select name="Оплата" required class="w-full p-2 rounded bg-gray-700 text-white">
          <option>Банковская карта</option>
          <option>СБП</option>
          <option>QIWI</option>
          <option>ЮMoney</option>
          <option>Kaspi.kz</option>
          <option>O!Деньги / Элсом</option>
          <option>Crypto</option>
        </select>

        <button type="submit" class="w-full py-2 bg-green-500 hover:bg-green-400 text-black rounded">Отправить заказ</button>
        <button type="button" onclick="closeModal()" class="w-full mt-2 py-2 bg-gray-700 hover:bg-gray-600 text-white rounded">Отмена</button>
      </form>
    </div>
  </div>

  <footer class="text-center mt-12 py-4 text-sm text-gray-400">
    &copy; 2025 Myxamet Shop. Все права защищены.
  </footer>

  <script>
    function openModal(product) {
      document.getElementById('productField').value = product;
      document.getElementById('modal').classList.remove('hidden');
    }

    function closeModal() {
      document.getElementById('modal').classList.add('hidden');
    }
  </script>
</body>
</html>
