Nginx Setup:
===========
1) https://github.paypal.com/ConsumerWeb-R/ppmenodeweb/wiki/PayPal.me-Guide-(for-P2P-folks)
2) replace content in `/usr/local/etc/nginx/nginx.conf`
   https://github.paypal.com/pgarciacamou/pgarciacamou/blob/master/nginx/nginx.conf
3) Change our port number in above link (3004 -> 8000): this will avoid having to do `PORT=3004 npx nps d.w` to run `p2pnodeweb`
4) If problem with self signed certificate please flow below link steps
   https://www.ateam-oracle.com/how-to-make-chrome-on-os-x-trust-a-self-signed-certificate
5) Please copy below code and update above of 'features' in 'config/development.json' p2pnodeweb
   "topos": {
     "host": "msmaster.qa.paypal.com"
   }
   rm node_modules/topos/toposcache.json
   sudo nginx // start the nginx
   //sudo nginx -s reload (if needed)
6) In the terminal, run the command `whoami` to get your current `user_id`. Then run `sudo chown -vhR pgarciacamou:admin /usr/local/var/run/nginx` (🚨replace `pgarciacamou` with your `user_id`). This will allow you to run `nginx` without using `sudo`; `sudo nginx` -> `nginx`, `sudo nginx -s reload` -> `nginx -s reload`, etc.

Power-up:
========

You can run Nginx for individual repos using Docker:

https://engineering.paypalcorp.com/confluence/display/P2PConsumer/Steps+to+run+multiple+node+apps+on+the+same+machine
