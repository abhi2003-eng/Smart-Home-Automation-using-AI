# Smart-Home-Automation-using-AI
import datetime

def auto_lighting(command):
    hour = datetime.datetime.now().hour
    if "light on" in command or (6 <= hour <= 18):
        print("Lights turned ON based on command/time.")
    elif "light off" in command or (hour < 6 or hour > 18):
        print("Lights turned OFF based on command/time.")

        import speech_recognition as sr

def listen_and_execute():
    r = sr.Recognizer()
    with sr.Microphone() as source:
        print("Listening for command...")
        audio = r.listen(source)
    try:
        command = r.recognize_google(audio)
        print(f"Command received: {command}")
        return command.lower()
    except sr.UnknownValueError:
        print("Sorry, I didn't catch that.")
        return ""

    main()
