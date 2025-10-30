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

import chromedriver_autoinstaller
chromedriver_autoinstaller.install()
import time

from selenium import webdriver
from selenium.webdriver.common.by import By

# Initialize the Chrome WebDriver
driver = webdriver.Chrome()

try:
    # Navigate to the checkboxes page
    driver.get("https://the-internet.herokuapp.com/checkboxes")

    # Find all checkbox elements
    checkboxes = driver.find_elements(By.CSS_SELECTOR, "input[type='checkbox']")

    # Check each checkbox if not already selected
    for cb in checkboxes:
        if not cb.is_selected():
            cb.click()
        print("Checked:", cb.is_selected())
    time.sleep(30)

finally:
    # Quit the driver
    driver.quit()
    ************************************************************
    import chromedriver_autoinstaller
chromedriver_autoinstaller.install()
import time

from selenium import webdriver

# Initialize the Chrome WebDriver
driver = webdriver.Chrome()

try:
    # Navigate to Google
    driver.get("https://www.google.com")
    
    # Save screenshot
    driver.save_screenshot("google.png")
    print("Screenshot saved!")
    time.sleep(30)
finally:
    # Quit the driver
    driver.quit()
    ********************************************************************************************************
    import chromedriver_autoinstaller
from selenium import webdriver
from selenium.webdriver.common.by import By
import time

chromedriver_autoinstaller.install()

# Initialize the Chrome WebDriver
driver = webdriver.Chrome()

try:
    # Navigate to the login page
    driver.get("https://the-internet.herokuapp.com/login")
    
    # Enter username and password
    driver.find_element(By.ID, "username").send_keys("tomsmith")
    driver.find_element(By.ID, "password").send_keys("SuperSecretPassword!")
    
    # Corrected locator for login button
    driver.find_element(By.CSS_SELECTOR, "button[type='submit']").click()
    
    # Retrieve and print the message
    message = driver.find_element(By.ID, "flash").text
    print("Message:", message)
    time.sleep(30)
finally:
    # Quit the driver
    driver.quit()
    ********************************************************************************
    import chromedriver_autoinstaller
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
import time

chromedriver_autoinstaller.install()

# Initialize the Chrome WebDriver
driver = webdriver.Chrome()

try:
    # Navigate to Google
    driver.get("https://www.google.com")
    
    # Find the search box and perform search
    search_box = driver.find_element(By.NAME, "q")
    search_box.send_keys("Python Selenium")
    search_box.send_keys(Keys.RETURN)
    
    # No explicit wait; may cause errors if page loads slowly
    results = driver.find_elements(By.CSS_SELECTOR, "h3")[:5]
    
    # Print the titles of the top 5 results
    for r in results:
        print(r.text)
    time.sleep(40)

finally:
    # Quit the driver
    driver.quit()
    ***********************************************************************
    import chromedriver_autoinstaller
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import Select
import time

chromedriver_autoinstaller.install()

# Initialize the Chrome WebDriver
driver = webdriver.Chrome()

try:
    # Navigate to the dropdown page
    driver.get("https://the-internet.herokuapp.com/dropdown")
    
    # Locate the dropdown element and create a Select object
    dropdown = Select(driver.find_element(By.ID, "dropdown"))
    
    # Select option by value (assuming '2' is a valid option; '3' may not exist)
    dropdown.select_by_value("2")
    
    # Print the text of the currently selected option
    print("Selected:", dropdown.first_selected_option.text)
    time.sleep(40)

finally:
    # Quit the driver
    driver.quit()
    ***************************************************************************************
    import chromedriver_autoinstaller
from selenium import webdriver
from selenium.webdriver.common.by import By
import time

chromedriver_autoinstaller.install()

# Initialize the Chrome WebDriver
driver = webdriver.Chrome()

try:
    # Navigate to the checkboxes page
    driver.get("https://the-internet.herokuapp.com/checkboxes")
    
    # Find all checkbox elements
    checkboxes = driver.find_elements(By.CSS_SELECTOR, "input[type='checkbox']")
    
    # Click each checkbox to toggle its state
    for cb in checkboxes:
        cb.click()
        # Print whether the checkbox is selected
        print("Checked:", cb.is_selected())
        time.sleep(40)

finally:
    # Quit the driver
    driver.quit()
    ***********************************************************************************************
    import chromedriver_autoinstaller
from selenium import webdriver
import time

chromedriver_autoinstaller.install()

# Initialize the Chrome WebDriver
driver = webdriver.Chrome()

try:
    # Navigate to Google
    driver.get("https://www.google.com")
    
    # ❌ Wrong path: missing filename extension or invalid directory
    driver.save_screenshot("/screenshots/google")
    print("Screenshot saved!")
    time.sleep(40)
except Exception as e:
    print(f"An error occurred: {e}")
    
finally:
    # Quit the driver
    driver.quit()
