---
tags:
  - python
  - datafetching
  - pypi
title: Beautiful Soup
---
# Basics
-   Beautiful Soup is a library that makes it easy to scrape information from web pages. It sits atop an HTML or XML parser, providing Pythonic idioms for iterating, searching, and modifying the parse tree. [PyPi](https://pypi.org/project/beautifulsoup4/)
- [Documentation](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)

# Notes
- [Repository Link](https://github.com/darkcohiba/100-days-of-python-udemy/tree/main/day-45)
- Import Beautiful Soup
```python
from bs4 import BeautifulSoup
```
- Initiate Beautiful Soup, passing in our HTML content and our parser
```python
with open('website.html') as web_file:  
contents = web_file.read()  
  
soup = BeautifulSoup(contents, "html.parser")
```
- If we are using a simple html page with a `<title></title>` element we can print it simply like this
```python
print(soup.title)
# output: <title>Angela's Personal Site</title>
```
- We can print our entire soup and also make it formatted with prettify
```python
print(soup)  
print(soup.prettify())
```
- We can print the first element found in the document by using dot notation on soup
```python
print(soup.li)  
print(soup.a)
```
- To print all of the elements in the HTML page we can use the findAll Method on our soup
```python
print(soup.findAll(name="li"))
# or
print(soup.find_all(name="li"))
```
- If we want to loop through all of our tags, we can create a for loop and either a method or simple dot notation
```python
all_anchor_tags = soup.findAll(name="a")  
for tag in all_anchor_tags:  
	print(tag.string)  
	print(tag.getText())
```
- We can also print the HREF with the get Method
```python
print(tag.get("href"))
```
- We can also search for things by a combination of element, id , etc
```python
heading = soup.find(name='h1', id="name", class_="className")
print(heading)
```
- We can use CSS selector convention to drill down into certain tags
```python
# all the matching items  
company_url = soup.select(selector="p a")  
# get the first  
company_url = soup.select_one(selector="p a")  
print(company_url)
```
- To parse a website with request we need to turn it into text first
```python
response = requests.get("https://news.ycombinator.com/")  
web_page = response.text  
soup = BeautifulSoup(web_page, "html.parser")  
print(soup.title)
```