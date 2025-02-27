# autoinsta
## A small Python project that automatically takes trending tik toks and uploads them to instagram.

This is an in-development automated social media tool, built on Selenium, that I am developing for fun.

I am currently also using the TikTokAPI for video retrieval. 

For an example of an instagram account that uses the bot, check out [@trendmeisters](https://www.instagram.com/trendmeisters/?hl=en)

## Recently Added
- [X] ffmpeg auto-padded videos
    
    *Automatically pads any TikTok content to fit the 4:3 Instagram Aspect Ratio* 
- [X] Docker Support
   
   *Added a basic Dockerfile that runs the bot via docker*

## Getting Started

Clone the repo
```
git clone https://github.com/Brannydonowt/autoinsta.git
```
### Running Via Docker
I have dockerized the project so that you can simply create a deployable docker image to run.
```
docker build -t autoinsta .
```
You **MUST** be running in headless mode for Docker to run succesfully.

I'm new to using Docker, so if there are any problems please raise an issue and I'll jump on it!

### Running Locally
install the required pip packages (requirements.txt file included)
```
pip install virtualenv (if you don't already have virtualenv installed)
virtualenv venv
source venv/bin/activate
pip install -r requirements.txt
```

TikTokApi uses the Playwright library. Therefore with a fresh install, you need to ensure that you run
*(due to this, you may have some problems running this bot on linux. I recommend using Docker if running locally doesn't work for you.)*
```
playwright install
```

Make sure you have a valid web driver installed and placed into your PATH for Selenium.
[Follow this link for more information on how to do that](https://pypi.org/project/selenium/)

Create a folder at the root called "profiles".
In this folder create a file called "instagram.pass", and write your login details inside as like so:
```
exampleaccount@example.com
examplepassword123
```
path should look like: *autoinsta/profiles/instagram.pass*

*.pass files are in the .gitignore, so will not be picked up when commiting, you can also remove the requirement for this file by manually entering your login details in the instagram.py.*
*To do this, go to instagram.py. Delete line 107 and enter your details in the place of usr and pwd on line 109*

You can now compile run bot.py to upload a single trending tiktok video to your instagram page.

You can also adjust and run scheduler.py to schedule posts every x minutes or at certain times throughout the day.
[Follow this link for more information on how to do that](https://pypi.org/project/schedule/)

### Cookies

[There are some issues that can occur related to the TikTokAPI](https://github.com/davidteather/TikTok-Api/issues/891). Most of these issues can be circumvented by logging into tik tok manually, scrolling through for a short time and then saving all of your cookies to a json file (at cookies/cookies.json)

This can be done using a browser extension [like this one.](https://add0n.com/cookie-editor.html)

## Development Plan
##### This is a hobby project, and so further development is not guaranteed, however below are some of the features I'd like to add.

- Post Likes
    - Automatically find posts of a certain type/hashtag and like x number of them
- Page Following
    - Automatically find relevant pages and follow x number of them
- Post Reels/Story's
- Video Editing
    - Automatically edit videos to include watermarks, corrected aspect ratios, captions.
- Commenting
    - Comment on relevant posts with reasonable messages (potentially using OpenAI to generate natural comments)






