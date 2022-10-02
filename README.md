# SiteSlite code:
import requests
from progressbar import ProgressBar

link = input("Gimme your URL: ")
heck = requests.get(link).text
heck1 = requests.get(link).content

try:
    if "www." or "https" or "http" in link:
        if str(200) in heck:
                ProgressBar()
                print("State: Ok")
                print(heck)
                b = input("Wants check more Y/N? ")
                if b == "Y" or "y":
                    ProgressBar()
                    print("State: Ok ")
                    print(heck1)
                else:
                    print(" ")
        else:
            ProgressBar()
            print("State: Not found ")
except Exception:
    ProgressBar()
    print("State: Error. Your URL or HTML.text is notfound.")
#progressbar code:
import math

def ProgressBar():
    def progressbar(progress, total):
        pesent = 100 * (progress / float(total))
        bar = '■' * int(pesent) + '-' * (100 - int(pesent))
        print(f"\r|{bar}| {pesent:.2f}%", end="\r")

    num = [x * 5 for x in range(2000, 3000)]
    results = []

    progressbar(0, len(num))
    for i, x in enumerate(num):
        results.append(math.factorial(x))
        progressbar(i + 1, len(num))
