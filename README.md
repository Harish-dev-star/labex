# labex
import chromedriver_autoinstaller
chromedriver_autoinstaller.install()

from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
import time

# Initialize the Chrome WebDriver
driver = webdriver.Chrome()

try:
    # Navigate to Wikipedia
    driver.get("https://www.wikipedia.org/")

    # Find the search box and perform a search
    search_box = driver.find_element(By.NAME, "search")
    search_box.send_keys("Selenium (software)")
    search_box.send_keys(Keys.RETURN)

    # Wait for the page to load
    time.sleep(40)

    # Extract and print the first paragraph
    first_paragraph = driver.find_element(By.CSS_SELECTOR, "p").text
    print("First Paragraph:", first_paragraph)

finally:
    # Quit the driver
    driver.quit()

    ***********************************************************************************************************************************
    import chromedriver_autoinstaller
chromedriver_autoinstaller.install()

from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
import time

# Initialize the Chrome WebDriver
driver = webdriver.Chrome()

try:
    # Navigate to Amazon India
    driver.get("https://www.amazon.in/")

    # Find the search box and enter "laptop"
    search_box = driver.find_element(By.ID, "twotabsearchtextbox")
    search_box.send_keys("laptop")
    search_box.send_keys(Keys.RETURN)

    # Wait for results to load
    time.sleep(30)

    # Find the first 5 product titles
    products = driver.find_elements(By.CSS_SELECTOR, "span.a-size-medium.a-color-base.a-text-normal")[:5]

    # Print the product titles
    for idx, product in enumerate(products, start=1):
        print(f"{idx}. {product.text}")

finally:
    # Quit the driver
    driver.quit()
    ***********************************************************************************************************
    import chromedriver_autoinstaller
from selenium import webdriver
from selenium.webdriver.support.ui import Select
from selenium.webdriver.common.by import By
import time

chromedriver_autoinstaller.install()

# Initialize the Chrome WebDriver
driver = webdriver.Chrome()

try:
    # Navigate to the dropdown page
    driver.get("https://the-internet.herokuapp.com/dropdown")
    
    # Locate the dropdown element
    dropdown = Select(driver.find_element(By.ID, "dropdown"))
    
    # Select "Option 2"
    dropdown.select_by_visible_text("Option 2")
    print("Selected:", dropdown.first_selected_option.text)
    time.sleep(50)
finally:
    # Quit the driver
    driver.quit()
