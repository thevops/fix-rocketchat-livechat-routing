# fix-rocketchat-livechat-routing
Fix RocketChat Livechat least amount routing method

# Problem
https://github.com/RocketChat/Rocket.Chat/issues/13134

# Solution

Clear counter everyday with script `clear_count.js`

```
conn = new Mongo();
db = conn.getDB("rocketchat");

db.rocketchat_livechat_department_agents.update({username: "kate"},{$set:{'count':0}})
db.rocketchat_livechat_department_agents.update({username: "jack"},{$set:{'count':0}})
```
(add this to cron)
