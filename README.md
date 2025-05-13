- 👋 Hi, I’m @dmitrijiks
- 👀 I’m interested in pithon
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
dmitrijiks/dmitrijiks is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->from telegram import Update
from telegram.ext import Updater, CommandHandler, CallbackContext

# Вставьте Ваш токен
TOKEN = 'YOUR_TELEGRAM_BOT_TOKEN'

def start(update: Update, context: CallbackContext) -> None:
    update.message.reply_text('Привет! Я бот для покупки и продажи NFT наклеек.')

def buy(update: Update, context: CallbackContext) -> None:
    update.message.reply_text('Введите ID наклейки, которую хотите купить.')

def sell(update: Update, context: CallbackContext) -> None:
    update.message.reply_text('Введите ID наклейки, которую хотите продать.')

def main():
    updater = Updater(TOKEN)
    dispatcher = updater.dispatcher

    dispatcher.add_handler(CommandHandler("start", start))
    dispatcher.add_handler(CommandHandler("buy", buy))
    dispatcher.add_handler(CommandHandler("sell", sell))

    updater.start_polling()
    updater.idle()

if __name__ == '__main__':
    main()

