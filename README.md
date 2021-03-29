# How to use

1. `pip install -r requirements.txt`
2. `python -m spacy download en_core_web_sm`
3. Make sure you actually have the right spacy model installed.<br> For example, install `en_core_web_sm` with the `python -m spacy download en_core_web_sm` command in the terminal.<br>
Next, fix this error:<br>
File `C:\Users\USER\AppData\Local\Programs\Python\Python37\lib\site-packages\chatterbot\tagging.py`, line 13, in __init__<br>
    `self.nlp = spacy.load(self.language.ISO_639_1.lower())`<br>
That is<br>
Open the `C:\Users\USER\AppData\Local\Programs\Python\Python37\lib\site-packages\chatterbot\tagging.py` file<br>
    Go to Line 13<br>
    Replace<br>
    `self.nlp = spacy.load(self.language.ISO_639_1.lower())` with<br>
<pre>if self.language.ISO_639_1.lower() == 'en':
	self.nlp = spacy.load('en_core_web_sm')
else:
    self.nlp = spacy.load(self.language.ISO_639_1.lower())</pre>
    
You will need to add more conditions for other languages you need to support
4. `python bot.py`
