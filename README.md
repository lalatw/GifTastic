# Trivia Game
Assignment_GifTastic

# Link to deployed site
https://lalatw.github.io/GifTastic/


# Images
![TriviaGame Assignment](assets/images/screenshot.png)

# Technology used
* html
* css
* javascript
* jQuery
* bootstrap
* API


# Code snippets


```

    function displayInfo() {
        var itemName = $(this).attr("data-name");
        var queryURL = "https://api.giphy.com/v1/gifs/search?q=food+" + itemName + "&rating=g&limit=10&api_key=TVxQvzKbz76RUCSYfQDXsZU5CHvX6uxY";
        $("#mainimages").empty();

        $.ajax ({
            url: queryURL,
            method: "GET"
        }) .then(function(response) {
            console.log(response);

            var results = response.data;

            for (var i=0; i<results.length; i++) {

                var dataImage = $("<img>");
                dataImage.attr("src", results[i].images.fixed_height_still.url);
                dataImage.attr("data-still", results[i].images.fixed_height_still.url);
                dataImage.attr("data-animate", results[i].images.fixed_height.url);
                dataImage.addClass("gif");
                dataImage.attr("data-state", "still");
    
    
                var newItemdiv = $('<div class="newItem">');
                var gifRating = results[i].rating;
                var divRating = $("<p>").text("Rating: " + gifRating);
                
                newItemdiv.append(divRating);
                newItemdiv.append(dataImage);
    
                $("#mainimages").prepend(newItemdiv);



            }
    
 
        }); 


    }


```


# Learning points
* Apply ajax call to get API data
* Create data attribute as a class to store data
* Use javascript along with jQuery to add or change the desired behavior of web page.
* Use jQuery click event to triger data display.






# Author 
[Shuhan Laura Lee](https://lalatw.github.io/GifTastic/)

* Portfolio : https://lalatw.github.io/Responsive-Portfolio/portfolio.html


# License
Standard MIT License
