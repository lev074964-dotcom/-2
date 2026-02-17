#простой бот






import telebot
import time
import random
    bot = telebot.TeleBot("Токен")
    
    @bot.message_handler(commands=['start'])
    def send_welcome(message):
        bot.reply_to(message, "Привет! Я твой Telegram бот. Напиши что-нибудь!")
    
    @bot.message_handler(commands=['hello'])
    def send_hello(message):
        bot.reply_to(message, "Привет! Как дела?")
    
    @bot.message_handler(commands=['bye'])
    def send_bye(message):
        bot.reply_to(message, "Пока! Удачи!")
    
    
    @bot.message_handler(func=lambda message: True)
    def echo_all(message):
        bot.reply_to(message, message.text)

    def set_timer(message):
        args = message.text.split()
    if len(args) > 1 and args[1].isdigit():
        sec = int(args[1])
        schedule.every(sec).seconds.do(beep, message.chat.id).tag(message.chat.id)
    else:
        bot.reply_to(message, 'Usage: /set <seconds>')

@bot.message_handler(commands=['mem'])
def send_mem(messasge):
    img_name = random.choise(images)
    with open('images/mem1.jpg', 'rb') as f:  
        bot.send_photo(message.chat.id, f)          

@bot.message_handler(commands=['шутка'])
def send_шутки(messasge):
    bot.reply_to(message, " Шутка№1 Штирлецу звонят по телефону и говорят вам наверно не спится без меня а он отвечает я смогу спица и без вас.   Шутка№2 Штирлецу стучат в дверь 40 раз он думает сороконожка 5 осминогов за дверью думают дурак")
    
    
    bot.polling()
