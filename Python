from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.chrome.service import Service
from selenium.webdriver.chrome.options import Options
from webdriver_manager.chrome import ChromeDriverManager
import random
import time

# Chrome options
chrome_options = Options()
chrome_options.add_argument("--headless")  # Tarayıcı arayüzü olmadan çalıştır
chrome_options.add_argument("--no-sandbox")
chrome_options.add_argument("--disable-dev-shm-usage")

# WebDriver kurulumu
service = Service(ChromeDriverManager().install())
driver = webdriver.Chrome(service=service, options=chrome_options)

# URL'ye git
url = "https://www.nissan.com.tr/services/sizi-arayalim.html?cid=psm_cmid=21787791240_grid=_adid=&gad_source=1&gclid=Cj0KCQiA4-y8BhC3ARIsAHmjC_H--BRWsl1B-3mXYcovYxG7O4vw40Vfl9ow0NsD1aE9u074H8LVOKwaAsRgEALw_wcB&gclsrc=aw.ds"
driver.get(url)

# Rastgele bilgi oluşturma fonksiyonu
def generate_random_info():
    names = ["John", "Jane", "Alice", "Bob"]
    surnames = ["Doe", "Smith", "Brown", "Johnson"]
    emails = ["example@example.com", "test@test.com", "hello@world.com"]
    return random.choice(names), random.choice(surnames), random.choice(emails)

# Formu doldurma
number_to_enter = "1234567890"  # Dosya başında vereceğiniz numara

# İsim
name_field = driver.find_element(By.ID, "firstName")
random_name, random_surname, random_email = generate_random_info()
name_field.send_keys(random_name)

# Soyisim
surname_field = driver.find_element(By.ID, "lastName")
surname_field.send_keys(random_surname)

# Telefon numarası
phone_field = driver.find_element(By.ID, "phoneNumber")
phone_field.send_keys(number_to_enter)

# E-posta
email_field = driver.find_element(By.ID, "emailAddress")
email_field.send_keys(random_email)

# Formu gönderme (eğer gerekiyorsa)
submit_button = driver.find_element(By.ID, "submitButton")
submit_button.click()

# İşlem tamamlandıktan sonra tarayıcıyı kapat
time.sleep(5)  # Formun gönderilmesi için bekleme süresi
driver.quit()
