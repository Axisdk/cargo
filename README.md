# 🚚 Cargo Platform — Monorepository

Этот репозиторий содержит весь код платформы карго-компании, включая клиентские приложения, административные панели, backend API и общие библиотеки.

---

## 🧱 Архитектура

Проект построен как **монорепозиторий**, что позволяет:
- переиспользовать код между приложениями
- централизовать бизнес-логику и типы
- упростить поддержку и развитие системы
- синхронизировать изменения между всеми частями платформы

---

## 📦 Структура проекта


apps/
├─ infosite # Публичный SSR сайт (маркетинг + SEO)
├─ dashboard # Личный кабинет клиента
├─ admin # Административная панель
└─ api # Backend (NestJS)

libs/
├─ shared-types # Общие TypeScript интерфейсы и DTO
├─ auth # Логика авторизации и guard'ы
├─ ui # Переиспользуемые UI компоненты
├─ cargo-domain # Бизнес-сущности (Shipment, Cargo, Invoice)
└─ utils # Общие утилиты

database/
├─ prisma # Схема БД
└─ migrations # Миграции

docker/
└─ configs # Docker и инфраструктурные конфигурации


---

## 🌐 Приложения

### 🏢 infosite
Публичный сайт компании.

**Функции:**
- SEO-оптимизированные страницы
- информация об услугах
- калькулятор доставки
- трекинг груза по номеру

---

### 👤 dashboard
Личный кабинет клиента.

**Функции:**
- авторизация пользователей
- список отправлений
- отслеживание статусов грузов
- история заказов
- документы и счета

---

### 🛠 admin
Административная панель.

**Функции:**
- управление пользователями
- управление заказами и грузами
- обновление статусов доставки
- аналитика и мониторинг

---

### ⚙️ api
Backend сервис (NestJS).

**Функции:**
- REST / GraphQL API
- бизнес-логика
- работа с базой данных
- авторизация и роли
- интеграции с внешними сервисами

---

## 🔗 Общие библиотеки

### shared-types
Общие интерфейсы между frontend и backend.

```ts
export interface Cargo {
  id: string;
  trackingNumber: string;
  status: CargoStatus;
}
auth

Модуль авторизации:

JWT
Guards
Roles
Interceptors
cargo-domain

Бизнес-логика системы:

Shipment
Cargo
Invoice
Customer
ui

Общие UI компоненты:

кнопки
таблицы
формы
модальные окна
⚙️ Технологии
Angular (SSR + SPA)
NestJS
PostgreSQL
Prisma
TypeScript
Docker
Nginx
🚀 Деплой

Каждое приложение разворачивается отдельно:

infosite → cargo.kz
dashboard → cabinet.cargo.kz
admin → admin.cargo.kz
api → api.cargo.kz

через reverse proxy (Nginx).

📌 Принципы архитектуры
Modular design
Separation of concerns
Shared business logic in libs
Single source of truth for types
Independent deployment of apps
🧠 Цель проекта

Создать масштабируемую платформу для управления карго-перевозками, включающую:

публичный сайт
клиентский кабинет
административную систему
backend API
📈 Статус

Проект находится в активной разработке.

👨‍💻 Автор

Danil Kupriyanov