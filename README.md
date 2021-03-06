vimeo_api extension for Contao Open Source CMS
==============================================

This extension allows you to embed the Vimeo videos and albums on your website. It supports displaying both public and private videos, using custom poster images, viewing video in the lightbox.

The module supports responsive images feature which is implemented by default in Contao.

![Alt text](../screenshots/screenshot.jpg?raw=true)

## Requirements

The only requirement is to have jQuery enabled on the page. If you want to also use the lightbox feature, please enable the ```j_colorbox``` template in the page layout settings.

## Configuration

In order to make it work, you have to create the Vimeo app at <https://developer.vimeo.com/apps/> and generate the personal access token. Then, in the Contao settings enter the following data:

1. Client ID (in Vimeo: Client Identifier)
2. Client secret (in Vimeo: Client Secrets)
3. Access token (in Vimeo: Personal access token)

Afterwards you can start creating the "Vimeo video" content elements. If something does not work, be sure to check the system logs.

## Clearing Vimeo cache

By default the extension caches video data and images fetched from Vimeo API to improve the overall performance. In case you need to clear the cache, go to the Maintenance module and purge the Vimeo cache.

## Rebuilding Vimeo cache

In case you would like to rebuild the images and data cache, you can go to the Maintenance module and rebuild it there. The script will perform an AJAX request for every Vimeo content element - it works similar to the rebuilding Contao search index.
 
Contrary to the clearing/purging the Vimeo cache it will not delete the cache but override it. This means the frontend will still be accessible in timely fashion but it can still display the old cache if the particular elements have not been processed yet.

## Displaying private videos

To display the Vimeo private videos, make sure that your access token has ```private``` scope enabled. You may also need to refine the settings of the video itself, allowing it to be displayed on desired websites.

## Upgrade from 1.x to 2.x

After installing the new version of the extension make sure to **purge** the Vimeo cache. This will delete the obsolete files. Then you should batch **rebuild** the whole cache again.