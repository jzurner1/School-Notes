# Description
This lab contains a file path traversal vulnerability in the display of product images.

To solve the lab, retrieve the contents of the `/etc/passwd` file.

# Process
I had never done a path traversal lab, but I had read about it passively. Opening the lab, the main page was a simple shop with products, each product having its own page. On each product page is an image, presumably the image mentioned in the description.

Having never done one before, my first guess was to open inspect element and directly alter the image source. Originally, the image was stored at `src="/image?filename=57.jpg">`, so I tried `src="/../../../../../../etc/passwd"`. This didn't do anything, but provided a "not found" error in the console.

Next, I tried in the URL. Normally, images are found at a relative path; the previous image would have been something like `website.com/image?=57.jpg`. Instead, I tried `website.com/../../../../../../etc/passwd`, which also returned "not found".

Next, I tried `website.com/image?filename=../../../../../../etc/passwd`. This time, what looked like a white square was returned. That meant, I assumed, that the file was found, but it wasn't returned in a readable format.

I returned to the main page, and to my surprise, I had completed the lab. Apparently one of the things i had done qualified as finding the file, and I was never actually meant to read it. I'll take it.