> [!success] Report
> - Now only one source will publish focus mode to mqtt at a given transition.
> - Along with deactivate signal, total time is being sent.
> - Latest subscribers to focus mode topic will receive the last signal.
> - Implemented Swagger on current repo.
> - Change the buttons,
> 	![[Pasted image 20260202172738.png]]
> - Addressible leds,
> 	- [tronic](https://tronic.lk/product/waterproof-led-strip-ws2812-addressable-pixel-led-60pcs) 
> 	- [daraz](https://www.daraz.lk/products/4mm5mm6mm10mm-addressable-ws2812-rgb-led-strip-light-individual-addressable-with-chasing-light-effect-suitable-for-home-i375308066-s2071190099.html?c=&channelLpJumpArgs=&clickTrackInfo=query%253Aled%252Blight%252Bstrip%252Baddressable%253Bnid%253A375308066%253Bsrc%253ALazadaMainSrp%253Brn%253A2c111f24ec4b43c12e9c137be74f6d98%253Bregion%253Alk%253Bsku%253A375308066_LK%253Bprice%253A1259%253Bclient%253Adesktop%253Bsupplier_id%253A1000193840551%253Bbiz_source%253Ah5_external%253Bslot%253A39%253Butlog_bucket_id%253A470687%253Basc_category_id%253A10000810%253Bitem_id%253A375308066%253Bsku_id%253A2071190099%253Bshop_id%253A242605%253BtemplateInfo%253A&configId=choice_LK_promotion&freeshipping=0&fs_ab=1&fuse_fs=&lang=en&location=Overseas&price=1259&priceCompare=skuId%3A2071190099%3Bsource%3Alazada-search-voucher%3Bsn%3A2c111f24ec4b43c12e9c137be74f6d98%3BoriginPrice%3A125900%3BdisplayPrice%3A125900%3BsinglePromotionId%3A50000023550001%3BsingleToolCode%3AshopPromPrice_choiceEarlyBird%3BvoucherPricePlugin%3A0%3Btimestamp%3A1770036318115&ratingscore=&request_id=2c111f24ec4b43c12e9c137be74f6d98&review=&sale=2&search=1&source=search&spm=a211g0.searchlist.list.39&stock=1&upItemIds=375308066)



---
# Issue with total time synching
### Old implementation
- When using multiple browsers, total time need to be synchronized. There for I publish total time with every deactivate signal. And assign it to all browser clients. 
- The issue is it create a unnecessary overhead in mqtt broker. And the logic was a bit hard to manage. 
- There for as a solution what I have done is only one will publish activate and deactivate. It will not trigger a reply. 
- But by doing that I came across another issue.

### New implementation
![[Pasted image 20260202170337.png]]
- Consider two browsers. One is open and other is not. You turn on the focus mode. After sometime you open the other browser if it was still authenticated it will show activation. 
- If you turn off the focus mode from the second browser. It will cause to publish the incorrect focus time to the mqtt. As above `Report` I have made the focus topics to be single source. There for after publishing the incorrect ones nothing happens.
- Here I could suggest to fetch the number of sessions complete within today on start up to synchroninze them. But if focus was deactivated prematurely, the displayed time would be different.
- Or if the total time is greater than the one received through mqtt publish it back.

---
