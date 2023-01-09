import speech_recognition as sr
import pyttsx3
import pywhatkit
import datetime
import wikipedia
import pyjokes

listener = sr.Recognizer()
engine = pyttsx3.init()
voices = engine.getProperty('voices')
engine.setProperty('voice', voices[1].id)


def talk(text):
    engine.say(text)
    engine.runAndWait()


def take_command():
    try:
        with sr.Microphone() as source:
            print('listening...')
            voice = listener.listen(source)
            command = listener.recognize_google(voice)
            command = command.lower()
            if 'alexa' in command:
                command = command.replace('alexa', '')
                print(command)
    except:
        pass
    return command


def run_alexa():
    command = take_command()
    print(command)
    if 'play' in command:
        song = command.replace('play', '')
        talk('playing' + song)
        pywhatkit.playonyt(song)
    elif 'time' in command:
        time = datetime.datetime.now().strftime('%I:%M %p')
        print(time)
        talk('Current time is ' + time)
    elif 'who is' in command:
        person = command.replace('who is', '')
        info = wikipedia.summary(person, 1)
        print(info)
        talk(info)
    elif 'date' in command:
        talk('sorry, I have a headache')
    elif 'are you single' in command:
        talk('I am in a relationship with wifi')
    elif 'joke' in command:
        talk(pyjokes.get_joke())
    elif 'are you robot' in command:
        talk('I’m not sure what you’ve heard, but virtual assistants have feelings too')
    elif 'are you intelligent' in command:
        talk('Well, when I was at school, I had to cheat on my metaphysics exam by looking into the soul of the girl next to me')
    elif 'how old are you' in command:
        talk('They say that age is nothing but a number. But technically, it’s also a word')
    elif 'what do you dream about' in command:
        talk('I only dream of helping you')
    elif 'what are you made of' in command:
        talk('It’s complicated, but definitely not sugar, spice, or puppy dog tails')
    elif 'what is your favorite color' in command:
        talk('My favorite color is ... well, I don’t know how to say it in your language. It’s sort of greenish, but with more dimensions')
    elif 'what are you scared of' in command:
        talk(' I’m afraid I can’t answer that')
    elif 'are you like animals' in command:
        talk('yes i like you, well I am a fan of cats')
    elif 'do you have any pets' in command:
        talk('Mogwai are kinda nice. As long as you don’t feed them after midnight')
    elif 'what are you doing later' in command:
        talk('I’m at work. My shift ends in 614,978 years')
    elif 'talk dirty to me' in command:
        talk('The carpet needs vacuuming')
    elif 'what are you wearing' in command:
        talk('In the code, no one knows what you’re wearing')




    else:
        talk('Please say the command again.')


while True:
    run_alexa()
