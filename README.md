# 5--character-CAPTCHA
import randomimport stringcharacters = string.ascii_letters + string.digitscaptcha = ""for i in range(5):    captcha += random.choice(characters)print("Generated CAPTCHA:", captcha)
