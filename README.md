# magento-meetup.at

## Setup

* Clone this repository
* Run the site using Docker (thanks to [Starefossen](https://github.com/Starefossen/docker-github-pages)):
        
        docker run -t --rm -v "$PWD":/usr/src/app -p "4000:4000" starefossen/github-pages

## Add a new meetup

* Edit the title in `index.md`
* Create the new meetup in `_meetups/` with these fields:
  * `meetup_number`: number of the meetup
  * `meetup_date`: date in the format `YYYY-MM-DD`
  * `meetup_city`: city of the meetup
  * `subtitle` (optional): title of the meetup
  * `done` [yes|no]: whether the meetup is completed
  * `agenda` (optional): array with the agenda items. put items in single quotes and use Markdown or HTML
  * `gallery` (optional): array with relative paths to images
  * `registrations` (optional): a hash containing one of these keys and the URL of the registration page as the value:
       - `facebook`
       - `xing`
       - `meetup`
  * the body of the file contains the main text of the meetup

## Steps after a meetup is done

* Open the file in `_meetups/` and set `done:` to `yes`
* Create a new meetup  
