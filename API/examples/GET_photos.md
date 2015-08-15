# Photo Resources

    GET photos

## Description
Returns a listing of twenty (up to one hundred) photos for a specified **[photo stream][]**.

***

## Requires authentication
* A valid Consumer Key must be provided in **consumer_key** parameter.
* Alternatively, a valid **[OAuth][]** request with an authorized Access Token will be accepted.

***

## Parameters
- **feature** _(required)_ — Photo stream to be retrieved. Default *fresh_today*. Recognized values:
    ###### Global features
    - 'popular' — Return photos in Popular.  Default sort: rating.
    - 'highest_rated' — Return photos that have been in Popular.  Default sort: highest_rating.
    - 'upcoming' — Return photos in Upcoming.  Default sort: time when Upcoming was reached.
    - 'editors' — Return photos in Editors' Choice.  Default sort: time when selected by an editor.
    - 'fresh_today' — Return photos in Fresh Today.  Default sort: time when reached fresh.
    - 'fresh_yesterday' — Return photos in Fresh Yesterday.  Default sort: same as 'fresh_today'.
    - 'fresh_week' — Return photos in Fresh This Week.  Default sort: same as 'fresh_today'.

    ###### Per-user features
    All per-user streams require a **user_id** or **username** parameter

    - 'user' - Return photos of a user, additional parameter 'user_id' or 'username' is required.  Default sort: time uploaded.
    - 'user_friends' — Return photos by users the specified user is following.  Default sort: time uploaded.
    - 'user_favorites' — Return photos added as favorites by the specified user, as displayed on **[http://500px.com/:username/favorites][]**.  Default sort: time favorited.

- **only** — String name of the **[category][]** to return photos from. **Note:** Case sensitive, separate multiple values with a comma.
- **exclude** — String name of the **[category][]** to exclude photos by. **Note:** Case sensitive, separate multiple values with a comma.
- **sort** — Sort photos in the specified order.
    ###### Recognized values:
    - 'created_at' — Sort by time of upload (note: for a request of a user's favorite photos, this sort order will retrieve the list in the order that the user added photos to their favorites list.)
    - 'rating' — Sort by rating
    - 'highest_rating' — Sort by the highest rating the photo reached
    - 'times_viewed' — Sort by view count
    - 'votes_count' — Sort by votes count
    - 'favorites_count' — Sort by favorites count
    - 'comments_count' — Sort by comments count
    - 'taken_at' — Sort by the original date of the image extracted from metadata (might not be available for all images)

- **sort_direction** — Control the order of the sorting.  You can provide a **sort_direction** without providing a **sort**, in which case the default sort for the requested feature will be adjusted.
    ###### Recognized values:
    - 'asc' — Sort in ascending order (lowest or least-recent first)
    - 'desc' — Sort in descending order (highest or most-recent first).  This is the default.

- **page** — Return a specific page in the photo stream. Page numbering is 1-based.
- **rpp** — The number of results to return. Can not be over 100, default 20.
- **image_size** — The photo size(s) to be returned. See the documentation on **[photo sizes][]**.


- **include_store** — If set to 1, returns market infomation about the photo.
    ###### Returned values:
    - 'store_download' — Boolean value if the picture is avaliable for HD Download purchase.
    - 'store_print' — Boolean value if the picture is avaliable for Canvas print purchase.

- **include_states** — If set to 1, returns state of the photo for the currently logged in user and authenticated request.
    ###### Returned values:
    - 'liked' — Boolean value whether the current user has liked this photo
    - 'favorited' — Boolean value whether the current user has favorited this photo
    - 'purchased' — Boolean value whether the current user has bought this photo

- **tags** — If set to 1, returns an array of tags for the photo.

***

## Return format
An array with the following keys and values:

- **feature** — Feature that is being returned.
- **filters** — Additional filters that were used:
    - 'category' — The ID of the **[category][]** that photos were filtered by;
    - 'user_id' — The ID of the user specified by 'user_id' or 'username' parameters;
    - 'friends_ids' — IDs of users the user specified is following;
- **current_page** — Number of the page that is returned.
- **total_pages** — Total number of pages in this feature's stream.
- **total_items** — Total number of items in this feature's stream.
- **photos** — An array of Photo objects in **[short format][https://github.com/500px/api-documentation/blob/master/basics/formats_and_terms.md#short-format]**.

***

## Errors
None

***

## Example
**Request**

    https://api.500px.com/v1/photos?feature=popular

**Return** __shortened for example purpose__
``` json
{
  "feature": "popular",
  "filters": {
      "category": false,
      "exclude": false
  },
  "current_page": 1,
  "total_pages": 250,
  "total_items": 5000,
  "photos": [
    {
      "id": 4910421,
      "name": "Orange or lemon",
      "description": "",
      "times_viewed": 709,
      "rating": 97.4,
      "created_at": "2012-02-09T02:27:16-05:00",
      "category": 0,
      "privacy": false,
      "width": 472,
      "height": 709,
      "votes_count": 88,
      "favorites_count": 26,
      "comments_count": 58,
      "nsfw": false,
      "image_url": "http://pcdn.500px.net/4910421/c4a10b46e857e33ed2df35749858a7e45690dae7/2.jpg",
      "user": {
        "id": 386047,
        "username": "Lluisdeharo",
        "firstname": "Lluis ",
        "lastname": "de Haro Sanchez",
        "city": "Sabadell",
        "country": "Catalunya",
        "fullname": "Lluis de Haro Sanchez",
        "userpic_url": "http://acdn.500px.net/386047/f76ed05530afec6d1d0bd985b98a91ce0ce49049/1.jpg?0",
        "upgrade_status": 0
      }
    },
    {
      "id": 4905955,
      "name": "R E S I G N E D",
      "description": "From the past of Tagus River, we have History and memories, some of them abandoned and disclaimed in their margins ...",
      "times_viewed": 842,
      "rating": 97.4,
      "created_at": "2012-02-08T19:00:13-05:00",
      "category": 0,
      "privacy": false,
      "width": 750,
      "height": 500,
      "votes_count": 69,
      "favorites_count": 34,
      "comments_count": 29,
      "nsfw": false,
      "image_url": "http://pcdn.500px.net/4905955/7e1a6be3d8319b3b7357c6390289b20c16a26111/2.jpg",
      "user": {
        "id": 350662,
        "username": "cresendephotography",
        "firstname": "Carlos",
        "lastname": "Resende",
        "city": "Forte da Casa",
        "country": "Portugal",
        "fullname": "Carlos Resende",
        "userpic_url": "http://acdn.500px.net/350662.jpg",
        "upgrade_status": 0
      }
    }
  ]
}
```

[photo stream]: https://github.com/500px/api-documentation/blob/master/basics/formats_and_terms.md#500px-photo-terms
[OAuth]: https://github.com/500px/api-documentation/tree/master/authentication
[http://500px.com/:username]: http://500px.com/iansobolev
[http://500px.com/:username/following]: http://500px.com/iansobolev/following
[http://500px.com/:username/favorites]: http://500px.com/iansobolev/favorites
[category]: https://github.com/500px/api-documentation/blob/master/basics/formats_and_terms.md#categories
[short format]: https://github.com/500px/api-documentation/blob/master/basics/formats_and_terms.md#short-format-1
[photo sizes]: https://github.com/500px/api-documentation/blob/master/basics/formats_and_terms.md#image-urls-and-image-sizes
