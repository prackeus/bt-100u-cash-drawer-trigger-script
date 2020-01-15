<h1>BT-100U Cash Drawer Driver Trigger</h1>

I was faced with a project where I had a web based point of sale system that needed to trigger the cash drawer without utilizing a receipt printer. I found this on Amazon: [BT-100U Cash Drawer Driver Trigger With USB Interface](https://www.amazon.com/gp/product/B00OM9ML2K/ref=ppx_yo_dt_b_asin_title_o03_s00?ie=UTF8&psc=1)

I ended up getting it to work but there's basically no documentation. My solution was to run a node server on the computer attached to the drawer. The site would submit an ajax call to hit that server when the drawer should open. The node server would run a python script that would send the signal to open the drawer. The node script and the python script are included here.

I set up the node script to run on start up on the raspberry pi by editing /etc/rc.local to have: /full/path/to/node /full/path/to/myscript.js < /dev/null &
