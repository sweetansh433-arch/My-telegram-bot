from telegram import Update
from telegram.ext import Application, CommandHandler, MessageHandler, filters, ContextTypes

TOKEN = "8706228105:AAFarTloOWqRGMSN8NzQivI7veB4AHR2bgk"

async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text("Hello! Main tumhara bot hu 🤖")

async def chat(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text(update.message.text)

app = Application.builder().toke=(8706228105:AAFarTloOWqRGMSN8NzQivI7veB4AHR2bgk).build()

app.add_handler(CommandHandler("start", start))
app.add_handler(MessageHandler(filters.TEXT, chat))

print("Bot running...")
app.run_polling()
