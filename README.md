# FB Marketplace Date Checker

This bookmarklet allows you to see the exact listing date of any Facebook Marketplace item.

### How to Install:
1. Copy the code below:
   ```javascript
   javascript:(function(){const html=document.documentElement.innerHTML,match=html.match(/"creation_time":(\d+)/);if(match&&match[1]){const postDate=new Date(1e3*match[1]),now=new Date(),diffMs=now-postDate,diffMins=Math.floor(diffMs/6e4),diffHrs=Math.floor(diffMins/60),diffDays=Math.floor(diffHrs/24);let output="";if(diffDays>0){let months=12*(now.getFullYear()-postDate.getFullYear())+(now.getMonth()-postDate.getMonth()),days=now.getDate()-postDate.getDate();days<0&&(months--,days+=new Date(now.getFullYear(),now.getMonth(),0).getDate());let ageStr=months>0?months+(1===months?" month ":" months ")+(days>0?"and "+days+(1===days?" day":" days"):""):days+(1===days?" day":" days");output="⏳ Age: "+ageStr+" old."}else output=diffHrs>0?"⏳ Posted: "+diffHrs+(1===diffHrs?" hour":" hours")+" ago.":"⏳ Posted: "+Math.max(1,diffMins)+(1===diffMins?" minute":" minutes")+" ago.";const options={year:"numeric",month:"long",day:"numeric"};alert("📅 Listed: "+postDate.toLocaleDateString("en-US",options)+"\n\n"+output)}else alert("Not found. Are you on a specific listing page?")})();
2. Right-click your Browser Bookmarks Bar and select Add Page.
3. Name it Check FB Date.
4. Paste the code into the URL field and save.

### How to Use:
Open any Facebook Marketplace listing and click the bookmark!
