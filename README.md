## Как запустить проект

### 1. Клонируйте репозиторий

Сначала загрузите проект на ваш компьютер:

```bash
git clone https://github.com/Bustle101/pract_3.git
cd pract_3
```

### 2. Установите зависимости

Перед запуском установите все необходимые пакеты:

```bash
npm install
```

### 3. Запустите серверы

Проект использует два сервера, каждый нужно запускать отдельно в новом терминале:

- **Каталог товаров** (порт 3000):

```bash
node catalog-server/server.js
```

- **Панель администратора / API** (порт 8080):

```bash
node admin-server/server.js
```

### 4. Откройте в браузере

- Каталог доступен по адресу: [http://localhost:3000](http://localhost:3000)  
- Админка и API работают по адресу: [http://localhost:8080](http://localhost:8080)

---

## Возможности API

> Ниже представлены примеры запросов для работы с сервером администратора.

### 🔹 Добавление товара

```js
fetch('http://localhost:8080/desserts', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
        name: "пончик",
        price: 200,
        description: "с посыпкой",
        categories: ["Десерты"]
    })
})
.then(res => res.json())
.then(data => console.log(data));
```

### 🔹 Обновление товара

```js
fetch('http://localhost:8080/desserts/1', {
    method: 'PUT',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
        price: 300,
        description: "с посыпкой и глазурью"
    })
})
.then(res => res.json())
.then(data => console.log(data));
```

### 🔹 Удаление товара

```js
fetch('http://localhost:8080/desserts/1', {
    method: 'DELETE'
})
.then(res => res.json())
.then(data => console.log(data));
```
