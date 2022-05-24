#Deploy

## Orchestrator & demo_stt

> make run-docker-bundle

## STT

```
cd tts 
make run-docker-eng-cpu
make run-docker-kin-cpu 
```

#Usage

##SIp Phone

Download and install a soft phone like Zoiper5, than configure sip account:
```
domain: asterisk.dev.mbaza.digital
username: sipuser
password: xsecret
```

- Dial: 770
- After a welcome message, you’ll need to select the language: dial “1” for english and “2” for kinyarwanda.
- After the beep you can ask a question and wait for a replay. You may press “#” to send the question quicker, silence detection works better when there is no background noize. 
- The process repeats itself after audio replay, with a new beep to let you know the chatbot is listening for a new question. 

##Demo Client / console

### installation

> pip install -r orchestrator/requirements.txt

### run interactive console

> python3 orchestrator/app/console.py

The following environment variables can be configured: 
- APP_LOG_LEVEL  = debug 
- RASA_API_URL   = http://localhost:5005/webhooks/rest/webhook
- TTS_API_URL    = http://localhost:6901

ENG example:
> TTS_API_URL=http://m1.dev.mbaza.digital:6901 RASA_API_URL=http://rasa.dev.mbaza.digital/webhooks/rest/webhook python3 orchestrator/app/console.py

KIN example:
> TTS_API_URL=http://m1.dev.mbaza.digital:6903 RASA_API_URL=http://kiny.rasa.dev.mbaza.digital/webhooks/rest/webhook python3 orchestrator/app/console.py
