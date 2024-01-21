## 1. Mood-Based Listening
**Description**: Uses Spotfy's API to get data about what music a user listened to when, as well as attributes of that music, and then provides mood-based analyses and recommendations to the user.

**Main Features**:
1. The user can get a 'mood report' (could be simple or detailed) for their listening on a specific day, week, month, year, etc. (think 'Spotify Wrapped' but more flexible and available whenever, and with a heavier focus on the mood/vibe of the music)
2. The user can 'Find Music with this Mood' once they've identified a timespan that they really enjoyed the music from. This will give more far-reaching results than Spotify's default recommandations.
3. The user can 'Share this Mood' to share the playlist+mood label with other users, as well as look at information about other users that they have shared.

**Two types of users**:
1. Looking at your own data shows you everything you could want to know.
2. Someone else looking at your data shows only a subset of all the data, perhaps customizable based on what you've chosen to share.

**Relevant Spotify API methods**:  
1. GET /audio-features/{id}
2. GET /audio-analysis/{id}
3. GET /recommendations
4. POST /users/{user_id}/playlists
5. PUT /playslists/{playlist_id}/tracks

## 2. Integration with setlist.fm
**Description**: Uses Spotify's API and setlist.fm's API to automatically add the setlist for a particular show as a playlist to the user's account. Sometimes people will do this for concerts already and you can just listen to their playlists, but it's harder to find good ones for smaller shows and often they are not organized in a way that makes sense to everyone.

**Main Features**:  
1. Authenticate with Spotify (if possible and secure) to get list of favorite artists/songs/etc.
2. Click on any of those artists or songs to see a list of live concerts involving them and the setlist.fm setlist for those concerts
3. Click 'Add as Playlist' to:
    1. Find a matching song in Spotify's database for each song in the setlist.fm setlist
    2. Create a new playlist in the user's Spotify account, appropriately titled for the given concert
    3. Show the user a screen that allows them to accept/reject additions to the playlist and add new songs if needed
    4. Add all of the selected songs to the new playlist


**Two Types of Users**: ?

**Relevant Spotify API methods**:
1. GET /me/top/{type}
2. GET /me/following
3. POST /users/{user_id}/playlists
4. POST /playlists/{playlist_id}/tracks
5. PUT /playlists/{playlist_id}/tracks
6. PUT /playlists/{playlist_id}

## 3. 