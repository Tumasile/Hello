# Python
#import selenium libraries to python
from selenium import webdriver

#import time for delay
from time import sleep

#import credentials
from configFiles import config
#initialise driver for the browser, selenium supports chrome and firefox 
driver = webdriver.Chrome("C:\\Users\\tchilunga\\AppData\\Local\\Programs\\Python\\Python36-32\\drivers\\chromedr\\chromedriver.exe")

#open and get the link
driver.get('https://github.com/login?return_to=%2Fcaetanus%2Fwindows-file-changes-notify%2Ftree%2Fmaster%2Fwinwatcher')

#delay
sleep(5)
#find element on the html page by inspect element
textArea = driver.find_element_by_id('login_field')

# type to the field
textArea.send_keys(config.userName)

#find element on the html page by inspect element
textArea = driver.find_element_by_id('password')

# type to the field
textArea.send_keys(config.passw1)

# find the button. inspect element, copy xpath from webpage
submit_button = driver.find_elements_by_xpath('//*[@id="login"]/form/div[4]/input[3]')[0]
# click submit button
submit_button.click()

#close connection
driver.close()
