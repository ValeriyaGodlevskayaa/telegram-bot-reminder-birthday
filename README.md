# Telegram Bot Reminder Birthday

## Description
> This chatbot helps users view their contacts, add new entries, and receive birthday notifications. 

## Test Task Description
```
Install Node-red
https://nodered.org/
Install postgres
https://www.postgresql.org/

Create a bot in telegram using this software that uses the telegram REST API
https://core.telegram.org/bots/api

For example:
A bot that registers users and allows them to save contacts and their birthdays. You can ask for the birthday of someone whom the user has saved, or get a list of everyone saved there.

What we want to see is an understanding of
- how to work with the REST API (i.e., we don't use a node special for Telegram)
- anatomy of HTTP requests and their different types
- working with the database (https://dbdiagram.io/home)
```

## Features:
    - View contacts
    - Add new contacts
    - Delete contact 
    - Search by name
    - Notifications about birthdays

## Libraries & Tools Used:
    - Node.js: v20.10.0
    - npm: 10.9.2
    - ngrok - for local testing of webhooks.
    - node-red-contrib-config@1.2.1 - stores API URL and token for Telegram.
    - node-red-contrib-postgresql@0.14.2 - PostgreSQL integration. 
    - Docker Compose – PostgreSQL setup.
    - Telegram Bot API - https://core.telegram.org/bots/api.

## Database Schema:
You can view the database schema created for this project at the following link:
[Database Schema](https://dbdiagram.io/d/bot-67c5b0c6263d6cf9a00b90e6)

## Installation
1. Clone repository:
   ```
   git clone https://github.com/ValeriyaGodlevskayaa/telegram-bot-reminder-birthday.git
   cd telegram-bot-reminder-birthday/projects/reminder-telegram-bot
   git clone https://github.com/ValeriyaGodlevskayaa/reminder-telegram-bot.git .
   ```
2. Navigate to the project directory and install dependencies::
   ```
   cd telegram-bot-reminder-birthday
   npm install
   ```
3. Start using Docker Compose:
   ```
   docker-compose up -d
   ```
4. Open Node-RED in your browser:
   ```
   http://127.0.0.1:1889/
   ```
5. Set up your Telegram bot after receiving a token from BotFather or use the pre-configured bot [@remindBirthday123_bot](https://t.me/remindBirthday123_bot) and save it in:
   ```
   node config telegram api:
      flow.api_url: https://api.telegram.org/bot
      flow.token: YOUR_TELEGRAM_BOT_TOKEN (or use this token: 7924096352:AAEvAsqxWNNF4H5115xTt0nZ8yBP9OSXqWU)
   ```
6. Run `ngrok' to create a public URL for webhooks:
   ```
      ngrok http 1889
   ```
   Copy the received HTTPS URL and use it to set up a webhook in Telegram in node: set webhook.

## Commands 
- `/start` - the start command that sends a welcome message.
- `/list` - show all commands.
- `/listcontact` - a list of contacts.
- `/listcontact {name}` - a list of contacts with a search by name (optional parameter).
- `/addcontact` - add a new contact.
- `/deletecontact` - delete contact by current user_id and selected id. 