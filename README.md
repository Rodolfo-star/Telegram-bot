# Telegram-bot
pip install python-telegram-bot
from telegram import Update
from telegram.ext import Updater, CommandHandler, MessageHandler, Filters, CallbackContext

TOKEN = "7937825193:AAEQugjec6S67qdRpFIw0srhEDYIBdSPMmM"

def start(update: Update, context: CallbackContext):
    update.message.reply_text("Olá! Sou um bot de reações. Envie algo e eu respondo!")

def react(update: Update, context: CallbackContext):
    text = update.message.text.lower()
    if "bom dia" in text:
        update.message.reply_text("🌞 Bom dia!")
    elif "obrigado" in text:
        update.message.reply_text("💖 De nada!")
    else:
        update.message.reply_text("👍 Recebido!")

updater = (Updater7937825193:AAEQugjec6S67qdRpFIw0srhEDYIBdSPMmM, use_context=True)
dp = updater.dispatcher
dp.add_handler(CommandHandler("start", start))
dp.add_handler(MessageHandler(Filters.text & ~Filters.command, react))

updater.start_polling()
updater.idle()
