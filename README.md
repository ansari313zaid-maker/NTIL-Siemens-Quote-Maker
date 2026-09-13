# NTIL Quotation Maker — Siemens Price Master Edition

This project embeds the supplied Siemens Limited price-list data effective 01.07.2026 as an offline product master.

## Main workflow
1. Type/search a Siemens product/article/reference number.
2. Tap **Find** or select a suggestion.
3. The official LP/MRP and price-list page are filled automatically.
4. Enter **Purchase Discount %** and **Sale Discount %** only.
5. The app calculates Purchase Rate, Sale Rate, Purchase Value, Selling Value and Margin.
6. Save the quotation to local history.
7. Export the customer quotation to PDF or the working quotation to Excel.
8. LP/MRP and discount columns can be shown/hidden in the customer-facing quotation.

## Price master
Asset: `app/src/main/assets/siemens_price_2026_07.tsv`
- 6,866 extracted official price entries from the supplied 440-page PDF.
- Search is case-insensitive and also supports normalized-code matching (ignoring punctuation), useful for entries such as `5SL41067RC` when a quotation uses a formatted variant such as `5SL4106-7RC`.
- Each result keeps the price-list page number and whether the page is identified as LP or MRP.

## GitHub Actions
`.github/workflows/build-apk.yml` builds a debug APK in the cloud, so a phone-only workflow can be used without Android Studio.

## Important pricing note
The supplied Siemens publication states that MRP/LP is subject to revision without prior notice and that list prices are exclusive of taxes. Update/import the product master whenever Siemens issues a newer price list.
