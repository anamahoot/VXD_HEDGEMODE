# tradingview-alert-webhook for binance-api (one-way mode)
TradingView Strategy Alert Webhook that buys and sells crypto with the Binance API
This script work only on one-way mode please disable Hegde mode or bot won't working.
# Script is compatible with the follwing strategy message
passphrase = input.string(defval='xxxx', title ='Bot Pass',group='═ Bot Setting ═')
leveragex  = input.int(125,title='leverage',group='═ Bot Setting ═',tooltip='"NOTHING" to do with Position size',minval=1)
string Alert_OpenLong       = '{"side": "OpenLong", "amount": "@{{strategy.order.contracts}}", "symbol": "{{ticker}}", "passphrase": "'+passphrase+'","leverage":"'+str.tostring(leveragex)+'"}'
string Alert_OpenShort      = '{"side": "OpenShort", "amount": "@{{strategy.order.contracts}}", "symbol": "{{ticker}}", "passphrase": "'+passphrase+'","leverage":"'+str.tostring(leveragex)+'"}'
string Alert_LongTP         = '{"side": "CloseLong", "amount": "@{{strategy.order.contracts}}", "symbol": "{{ticker}}", "passphrase": "'+passphrase+'","leverage":"'+str.tostring(leveragex)+'"}'
string Alert_ShortTP        = '{"side": "CloseShort", "amount": "@{{strategy.order.contracts}}", "symbol": "{{ticker}}", "passphrase": "'+passphrase+'","leverage":"'+str.tostring(leveragex)+'"}'
var message_closelong       = '{"side": "CloseLong", "amount": "%100", "symbol": "{{ticker}}", "passphrase": "'+passphrase+'","leverage":"'+str.tostring(leveragex)+'"}'
var message_closeshort      = '{"side": "CloseShort", "amount": "%100", "symbol": "{{ticker}}", "passphrase": "'+passphrase+'","leverage":"'+str.tostring(leveragex)+'"}'
string Alert_StopLosslong   = '{"side": "CloseLong", "amount": "%100", "symbol": "{{ticker}}", "passphrase": "'+passphrase+'","leverage":"'+str.tostring(leveragex)+'"}'
string Alert_StopLossshort  = '{"side": "CloseShort", "amount": "%100", "symbol": "{{ticker}}", "passphrase": "'+passphrase+'","leverage":"'+str.tostring(leveragex)+'"}'
#Sample payload 
{"side":"OpenShort","amount":"@0.006","symbol":"BTCUSDTPERP","passphrase":"1234","leverage":"125"}
# There is 8 Vars Setting for HEROKU
1. API_KEY    	= your api key
2. API_SECRET	= your api secret key
3. LINE_TOKEN   = your Line-notify token can be genarated @https://notify-bot.line.me/en/
4. BOT_NAME		= any name
5. FREEBALANCE	= Min balance for trade(Bot will Halted if FREEBALANCE < Equity)
6. SECRET_KEY	= your passphrase form tradingview signal
7. ORDER_ENABLE = "TRUE" = Enable Bots "FALSE" = Disable Bots
8. ReOpenOrder	= "on" = book order again if order not filled or fail "off" = disable 
# YouTube tutorial on how to use this code (Thai)
https://youtu.be/-4gHb5PiC2I
#mod and dev by DR.AKN

