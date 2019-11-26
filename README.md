# Display_protosem
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
          
### Code for the Web app   
   Given below is a step by step process to create a dynamic website for displaying the top scorers in a leader board and running an in host server.
## HOME PAGE:
        
        
1.	Create a HTML file for the homepage with the required buttons. For example: LEADERBOARD, INNOVATION CONCEPTS, NEWS, etc. 
2.	Link these buttons to the respective html files for each option. Here is an example of how to link the “Leader board” button in the home page file to the “toplb.html” file for the leader board:

3.	Add styles to the code using a CSS file and link it to the html file.
     
4.	Now, you have a homepage to navigate to different segments of the website. The html codes are present in the “templates” folder above. For the CSS files, open the “static” folder.

### Auto updation of leaderboard

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
