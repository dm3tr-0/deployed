# lending
[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&pause=1000&color=71F70E&width=435&lines=%D1%83%D0%B6%D0%B5+%D0%BF%D0%BE%D1%87%D1%82%D0%B8)](https://git.io/typing-svg)

## Описание проекта
Веб-приложение мини-лендинг

🌐 **Демо**: [на render.com](https://lending-7k8v.onrender.com/)  (пока не задеплоил, но на локалке все работает )

📋 **ТЗ**: [Паспорт проекта](https://github.com/user-attachments/files/19212442/-25391.pdf)

**🖋🖌** [Фигма](https://www.figma.com/design/CgJLh9D60VDmD9tKEAmul2/Land-Craft?node-id=0-1&t=b6ezZSqBbytJRdue-1)

## 🚀 Возможности
- Выбор шаблона сайта
- Редактирование шаблона и экспорт в zip
- Интуитивно понятный веб-интерфейс

## 🛠 Установка

### Клонирование репозитория
```bash
git clone https://github.com/dm3tr-0/lending.git
cd lending
```

### Установка зависимостей
```bash
npm install
```

### 🖥 Запуск сервера
```bash
node server.js
```

### 🖥 Запуск фронта
```bash
npm run dev
```

### Настройка бд
```bash
postgres:1234
localhost:5432
db: langing_constructor
```

```
CREATE TABLE users (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    firebase_uid TEXT NOT NULL UNIQUE,
    email TEXT NOT NULL UNIQUE,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

CREATE TABLE templates (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    name TEXT NOT NULL,
    description TEXT,
    html_content TEXT NOT NULL,
    thumbnail_url TEXT,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
    is_active BOOLEAN DEFAULT TRUE
);

CREATE TABLE landings (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID REFERENCES users(id) ON DELETE CASCADE,
    template_id UUID REFERENCES templates(id) ON DELETE SET NULL,
    name TEXT NOT NULL,
    html_content TEXT NOT NULL,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
    updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);
```

## 📂 Структура проекта
```bash
empty yet
```

## 🔑 Стек

- Vite
- TypeScript
- React
- shadcn-ui
- Tailwind CSS
- firebase
- PostgreSQL
- Express
- GrapeJS
