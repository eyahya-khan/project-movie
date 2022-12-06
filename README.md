# Project Movies
Its an app of displaying movie list from API and details of specific movie when click on it.

## Using the API ⚡️

You will need to register an account with [themoviedb.org](https://www.themoviedb.org/) and then register for an API key in order to use the API.

When signing up for an API key, it asks a bunch of questions about what the application is for, but don't worry - we've contacted themoviedb.org and checked that they're OK with you all using the API for this purpose and it's all good in the hood. So, this is what you need to do:

1. Signup for [themoviedb.org](https://www.themoviedb.org/account/signup)
2. Go to [https://www.themoviedb.org/settings/api/request](https://www.themoviedb.org/settings/api/request)
3. Select 'developer' & accept the terms
4. Fill in the form requesting an API. You need to select 'Website' in the dropdown and say the use is for Technigo.
5. Submit the form and you should be approved automatically. Copy the v3 API key from the following page.

### *Fetching popular movies for the list page*

[https://api.themoviedb.org/3/movie/popular?api_key={api_key}&language=en-US&page=1](https://api.themoviedb.org/3/movie/popular?api_key=%7Bapi_key%7D&language=en-US&page=1)

*Don't forget to replace {api_key} with your API key if you copy and paste this*

### *Fetching a movie's details*

[https://api.themoviedb.org/3/movie/{movie_id}?api_key={api_key}&language=en-US](https://api.themoviedb.org/3/movie/%7Bmovie_id%7D?api_key=%7Bapi_key%7D&language=en-US)

*Don't forget to replace {api_key} with your API key and {movie_id} with the id you get from the url via react-router if you copy and paste this*

## Requirements 🧪

Your project should fulfill the **🔵  Blue Level** and all of the **General Requirements.** Use the **🔴  Red Level** and **⚫  Black Level** to push your knowledge to the next level!

### **🔵  Blue Level (Minimum Requirements)**

- Your app should have at least two pages - one showing a list of movies and one showing details
- You should follow the design from our example (but it's ok to change things - just try to make it look nice). Use styled-components or regular CSS.

### **🔴  Red Level (Intermediary Goals)**

- Show a 'not found' page if you try to visit a movie detail page with an invalid movie ID (so the user has tried to enter an ID themselves, most likely).
    - **Hint**
        
        In this case, when you send a movie detail request with a movie ID which doesn't exist in the API, the API returns with a 404 response. You can use `.catch()` on your promise to catch this exception and toggle some sort of 'error' state which can be used to show an error page.
        
- **Handle loading states** - The API responds quite quickly, but if you're on a slow network then you'd be faced with a black screen until the response comes back. During this time, you could show a loading message or spinner of some sort on the page.
    - **Hint**
        
        Use something like `const [loading, setLoading] = useState(true)` to make it so the page is loading by default, then call `setLoading(false)` once you get the response back from the API.
        
        You could also investigate how to handle the loading of images - or show plain text by default and then use CSS to place the image over the text (using absolute positioning). This way, if the images take a long time to load, the user still sees something relevant.
        

### **⚫  Black Level (Advanced Goals)**

- On the homepage where you list popular movies, you could add a dropdown to change the list. For example, you could toggle between popular, upcoming, and new releases.
    - **Hint**
        
        To implement this, you'd need a new item in your state and connect it to a `<select>`. When the value changes (`useEffect`), you can send a new API request to the appropriate API endpoint and replace your list of movies with the new data.
        
- **More pages** - When you load a movie, you get a lot of information in the API response, such as a collection it belongs to, genres it has, or the companies involved with producing the film. Each of these has an API endpoint that can be used to fetch more information about that entity. You could use this data to make links from your movie page to another page. Take a look through the documentation and be creative! 🎨

## View it live

https://gentle-empanada-7989b9.netlify.app
