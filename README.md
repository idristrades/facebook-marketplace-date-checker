# FB Marketplace Date Checker

This bookmarklet allows you to see the exact listing date of any Facebook Marketplace item.

### How to Install:
1. Copy the code below:
   ```javascript
   javascript:(function(){const html=document.documentElement.innerHTML;const match=html.match(/"creation_time":(\d+)/);if(match&&match[1]){const postDate=new Date(match[1]*1000);const now=new Date();const diffDays=Math.floor((now-postDate)/(1000*60*60*24));let timeLabel;if(diffDays<30){timeLabel=diffDays+" days old";}else if(diffDays<365){const months=Math.floor(diffDays/30.44);timeLabel=months+(months===1?" month old":" months old");}else{const years=Math.floor(diffDays/365.25);timeLabel=years+(years===1?" year old":" years old");}const options={year:'numeric',month:'long',day:'numeric'};alert("📅 Listed on: "+postDate.toLocaleDateString('en-US',options)+"\n\n⏳ Age: "+timeLabel);}else{alert("Date not found. Make sure you are on a specific listing page.");}})();
2. Right-click your Browser Bookmarks Bar and select Add Page.
3. Name it Check FB Date.
4. Paste the code into the URL field and save.

### How to Use:
Open any Facebook Marketplace listing and click the bookmark!
