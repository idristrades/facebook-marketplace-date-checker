# FB Marketplace Date Checker

This bookmarklet allows you to see the exact listing date of any Facebook Marketplace item.

### How to Install:
1. Copy the code below:
   ```javascript
   javascript:(function(){const html=document.documentElement.innerHTML;const match=html.match(/"creation_time":(\d+)/);if(match&&match[1]){const postDate=new Date(match[1]*1000);const now=new Date();let months=(now.getFullYear()-postDate.getFullYear())*12+(now.getMonth()-postDate.getMonth());let days=now.getDate()-postDate.getDate();if(days<0){months--;const lastMonth=new Date(now.getFullYear(),now.getMonth(),0).getDate();days+=lastMonth;}let ageStr=months>0?months+(months===1?" month ":" months ")+(days>0?"and "+days+(days===1?" day":" days"):"") : days+(days===1?" day":" days");const options={year:'numeric',month:'long',day:'numeric'};alert("📅 Listed: "+postDate.toLocaleDateString('en-US',options)+"\n\n⏳ Age: "+ageStr+" old.");}else{alert("Not found. Are you on a specific listing page?");}})();
2. Right-click your Browser Bookmarks Bar and select Add Page.
3. Name it Check FB Date.
4. Paste the code into the URL field and save.

### How to Use:
Open any Facebook Marketplace listing and click the bookmark!
