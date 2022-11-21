import bs4
import requests

# result = requests.get("https://www.videoschool.com/")
# soup = bs4.BeautifulSoup(result.text, 'html.parser')

# Print as a list
# print(soup.select('title'))
# Print outside of list
# print(soup.select('title')[0])
# Print without tags
# print(soup.select('title')[0].getText())
# Get all h5 elements
# central_block = soup.select('.fusion-text.fusion-text-1 h5')
# for h in central_block:
#    print(h.getText())

# download picture
# result = requests.get('https://www.videoschool.com/photography/')
# soup = bs4.BeautifulSoup(result.text, 'html.parser')
# images = soup.select('.img-responsive')[0]['src']
# print(images)
# image1 = requests.get(images)
# f = open('my_image.jpg', 'wb')
# f.write(image1.content)
# f.close()

# get first title on first page
# basic_url = 'http://books.toscrape.com/catalogue/page-{}.html'
# result = requests.get(basic_url.format('1'))
# soup = bs4.BeautifulSoup(result.text, 'html.parser')
# books = soup.select('.product_pod')
# example = books[0].select('a')[1]['title']
# print(example)

# create URL without page number
basic_url = 'http://books.toscrape.com/catalogue/page-{}.html'

#List of of 4 or 5 star titles
high_rated_titles = []

# iterate pages
for page in range (1, 51):
    #create soup on each page
    url_page = basic_url.format(page)
    result = requests.get(url_page)
    soup = bs4.BeautifulSoup(result.text, 'html.parser')

    # Select data of books
    books = soup.select('.product_pod')

    # Iterate books
    for book in books:

        #check if 4 or 5 stars
        if len(book.select('.star-rating.Four')) != 0 or len(book.select('.star-rating.Five')) != 0:

            # Store title in variable
            book_title = book.select('a')[1]['title']

            # add book to list
            high_rated_titles.append(book_title)

# show 4 or 5 start books
for b in high_rated_titles:
    print(b)
