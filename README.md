# FB Marketplace Date Checker

This bookmarklet allows you to see the exact listing date of any Facebook Marketplace item.

### How to Install:
1. Copy the code below:
   ```javascript
   javascript:(function(){const html=document.documentElement.innerHTML;const match=html.match(/"creation_time":(\d+)/);if(match&&match[1]){const date=new Date(match[1]*1000);const options={year:'numeric',month:'long',day:'numeric',hour:'numeric',minute:'numeric'};alert("Listed on: "+date.toLocaleDateString('en-US',options));}else{alert("Date not found. Make sure you are on a specific listing page.");}})();
