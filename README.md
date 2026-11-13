# Sakany-Rental-Platform
Sakany-Rental-Platform Bilingual (Arabic/English) rental listing platform for Egypt that connects property owners directly with renters. Built with PHP, MySQL and JavaScript: listings with video, search by governorate, city and keyword.

# Sakany: Direct Rental Platform for Egypt

Sakany connects property owners directly with renters, with no broker in between. Owners publish a listing with price, location and an optional walkthrough video, and renters search and filter the listings. The business idea, described in the pitch deck, is a flat 10% fee on the rent.

## Features
- Publish a listing: owner name, phone, title, description, governorate, city, price and an optional video
- Search by governorate, city or keyword (latest 100 listings, newest first)
- Listing page with the video and the owner's contact details
- Video preview on the listing cards when hovering
- Arabic and English interface, with right-to-left layout for Arabic
- Governorate and city dropdowns that update together, covering 27 governorates (`assets/data/eg_locations.json`)
- Contact page

## Tech stack
PHP (mysqli), MySQL, JavaScript, CSS

## Project structure
```
index.php            Home page, search and listing grid
add.php              Add listing form and upload handling
view.php             Single listing page
contact.php          Contact page
includes/db.php      Database connection
includes/i18n.php    Arabic/English strings and language switch
assets/              CSS, JavaScript and the location dataset
sql/create_db.sql    Database schema
sakani.pptx          Pitch deck (business idea, Arabic)
main.txt             Short project description (Arabic)
```

## Database
One table, `apartments`: owner name, phone, title, description, governorate, city, price, rooms, bathrooms, furnished, family-only, video file and creation time.

## Run it locally
1. Install XAMPP or WAMP and start Apache and MySQL
2. Copy the project folder into `htdocs`
3. Import `sql/create_db.sql` (creates the `rentease_db` database)
4. Set your own database user and password in `includes/db.php`
5. Open `http://localhost/<folder>/index.php`

Uploaded videos are saved to `uploads/videos/`, which is created on the first upload.

## Security
Implemented:
- Prepared statements for inserting listings
- Output escaped with `htmlspecialchars`
- Listing ID cast to an integer
- Video upload limited to an extension allow-list (mp4, webm, ogg, mov)

Known limitations and next steps:
- Move the search query to prepared statements
- Remove the double escaping in `add.php` (escape and prepared statement together)
- Add accounts and CSRF tokens
- Validate uploads by real MIME type and size, and rename uploaded files
- Use a limited database user instead of `root`

## Roadmap
The pitch deck also describes owner verification, in-platform messaging and a ratings system. These are planned ideas and are not built yet.

## Screenshots
(add: home page, a listing page, the add-listing form)

## My role
(write 1-2 lines)
