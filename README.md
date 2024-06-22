## Bounty Target for adding printable receipt after payment.

Enhance the LNbits TPOS extension by adding functionality to handle payment JSONs and generate printable receipts. After a payment is received and processed, a "Print Receipt" button should appear on the TPOS screen, allowing users to print the receipt. Ensure compatibility with devices that do not have a printer by providing alternative options.

The bounty will be paid by me once the changes are merged into lnbits main. 

**Action after setteled payment**
1) Successfully handle ´payment´ object JSON, extracting necessary details.
2) Generate a structured receipt based on the extracted payment information.
3) Display a "Print Receipt" button or pop up on the TPOS screen after a payment is processed. (+ add print button in "last sales" as well)
4) Print the receipt when the "Print Receipt" button is clicked.


![print_3](https://github.com/DoktorShift/tpos_receipt_print/assets/106493492/9a99ec7a-ba07-4a45-8cc8-40599459c507)

**Steps to achieve Bounty**
1. Payment JSON Handling:
   -  Extract the 'payment' object from the received JSON

2. Printable Receipt Generation:
   -  Create a visually appealing receipt format that includes relevant payment details. [Could be a source](https://github.com/lnbits/tpos-receipt-printer/blob/main/firmware/src/print.h#L214)

3. Implement functionality to detect if the device has an available printer.
   -  Provide alternative options if no printer is detected.

4. UI Enhancement:
   -  Modify the TPOS screen to display a "Print Receipt" button after the payment is successfully processed. (see above screenshot left)
   -  Modify TPoS receipt "last payments" to print receipt even after the payment process is finished. (see above Screenshot right)

## Achievment example


https://github.com/DoktorShift/tpos_receipt_print/assets/106493492/e926a0dd-4adc-45e4-bc39-84ee11a668c3




## Contribute:
You want to contribute but lack of skillz? You can [Donate](https://timecatcher.lnbits.de/tipjar/31) to enhance the bounty and make it attractive for developer to code this.


## Restrictions
Do not add dependencies, LNbits has plenty of dependencies you can use.
