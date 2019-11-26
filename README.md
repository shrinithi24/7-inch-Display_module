# INTERACTIVE DATA VISUALIZER
  This project is done to display the happenings inside a classroom/workspace for to the view of trespassers willing to know the sum up of the whole happening. Here,we use a 7 inch display powered up by raspberry Pi 3 and a website showcasing the profiles and happenings.
 ![alt-text](https://github.com/shrinithi24/Display_protosem/blob/master/Pi_display(1).jpg)
## Components Used
          Raspbeery pi 3
          7 inch display
          HDMI cable
          Power up cord
         
### Explanation
  Connect the Raspberry pi 3 installed with proper OS to a 7 inch display and then power the pi.Now,make sure that the backlight switch of display is ON.
  
          Display HDMI to pi's receiving HDMI end
          
          Touch end cable of diplay to Pi
          
          Power cord to Pi
          
### Explanation of website   
   Given below is a step by step process to create a dynamic website for displaying the top scorers in a leader board via data mined from google sheets and running an in host server.
## HOME PAGE:
  ![alt-text](https://github.com/shrinithi24/7-inch-Display_module/blob/master/1.PNG?raw=true)
        
        
1.	Create a HTML file for the homepage with the required buttons. For example: LEADERBOARD, INNOVATION CONCEPTS, NEWS, etc. 
2.	Link these buttons to the respective html files for each option. Here is an example of how to link the “Leader board” button in the home page file to the “toplb.html” file for the leader board:

                   <button class="button" style="vertical-
                   align:middle;color: black; "> <span><a href="./toplb.html ">Leaderboard</a></span>
                   </button>
                   
 3.	Add styles to the code using a CSS file and link it to the html file.
                
                <link rel="stylesheet" href="db.css">
     
4.	Now, you have a homepage to navigate to different segments of the website. The html codes are present in the “templates” folder above. For the CSS files, open the “static” folder.

### Auto updation of leaderboard

  ![alt-text](https://github.com/shrinithi24/7-inch-Display_module/blob/master/2.PNG?raw=true)

1.	Create a table for displaying the names of the top scorers in the html code:
<table style="width:100%" class="table table bordered table-striped" id="testTable">
                                  
      {%  for topper in toppers %}
      <tr>
      <th> {{topper}}</th>
      </tr>
      {% endfor %}
      </table>
 This loop will fetch the names from the google sheet through an google API call.
 
2.	 Steps for Google API call: please refer to the given link to fetch real time data from a google sheet and display it in the website.
https://www.twilio.com/blog/2017/02/an-easy-way-to-read-and-write-to-a-google-spreadsheet-in-python.html

3.	Again, add CSS styles to the leader board.

### SLIDER IN HTML:
        
   ![alt-text](https://github.com/shrinithi24/7-inch-Display_module/blob/master/3.PNG?raw=true)

1.	To have a slideshow of images in your dashboard, you can use this java script code to display multiple pictures with play, pause, previous and next options:

           var imgNumber = 0;
           var path = ["001.jpg","002.jpg","003.jpg","004.jpg"

  
           ];//add your images here
           var numberOfImg = path.length;
           var timer = null;

            function slide() {
            imgNumber = (imgNumber + 1) % path.length;
            console.log(imgNumber);
            document.getElementById("imgSlideshow").src = path[imgNumber];
            changeCounter(imgNumber + 1, numberOfImg);
           }
  
            function setTimer() {
            if (timer) {
            clearInterval(timer);
            timer = null;
            } else {
            timer = setInterval(slide, 2000);
            }
            return false;
          }


            function previousImage() {
            --imgNumber;
            if (imgNumber < 0) {
            imgNumber = numberOfImg - 1;
             }
             document.getElementById("imgSlideshow").src = path[imgNumber];
             changeCounter(imgNumber + 1, numberOfImg);
             return false;
           }

            function nextImage() {
            ++imgNumber;
            if (imgNumber > (numberOfImg - 1)) {
            imgNumber = 0;
            }
           document.getElementById("imgSlideshow").src = path[imgNumber];
           changeCounter(imgNumber + 1, numberOfImg);
           return false;
          }

            function changeCounter(cur, total) {
            document.getElementById("counter").innerHTML = cur + "/" + total;
           }
            document.getElementById("counter").innerHTML = 1 + "/" + path.length;
            
2.	Call this JavaScript code in the html file for the dashboard and you are good to go.

### HOSTING A DJANGO SERVER:
1.	Once, you are ready with all the html files and the google API call running, create a Django application by following the steps given in the link:

https://docs.djangoproject.com/en/2.2/intro/tutorial01/

2.	Create a model for your app as described in the documentation and then migrate the database.
3.	Run the server using the run server command in the terminal.

### ALTERNATE HOSTING USING Java Script code:
1.	If you are not using Django, you can run the code below in the terminal using node <name>.js command:
  
         var connect = require('connect');
         var serveStatic = require('serve-static');
         connect().use(serveStatic(__dirname)).listen(3000, function(){
         console.log('Server running on 3000...');
         });

2.	Now your website is locally hosted in the port number 3000 for the above given example and you can access it through any browser.
3.	You can also host the website in different servers by hosting through the IP address of the server the code is running in. Make sure to connect both the servers to the same network connection. 

        Example: 127.0.0.1:3000/


  Here we go, your website is ready to use.

