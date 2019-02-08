# mailspring_translation_plugin
translation plugin for mailspring

from requests import get
from json import dumps

def getUrl(sourceLang, targetLang, sourceText):
	return "https://translate.googleapis.com/translate_a/single?client=gtx&sl={}&tl={}&dt=t&q={}".format(sourceLang, targetLang, sourceText)

url = getUrl('en', 'nl', 'bread')

response = get(url)
print(response.text)

res = response.json()

print(res.__class__)
print("translated text is : ", res[0][0][0])
