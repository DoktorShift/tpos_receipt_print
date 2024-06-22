## Bounty Target for adding printable receipt after payment.

Enhance the LNbits TPOS extension by adding functionality to handle payment JSONs and generate printable receipts. After a payment is received and processed, a "Print Receipt" button should appear on the TPOS screen, allowing users to print the receipt. Ensure compatibility with devices that do not have a printer by providing alternative options.

**Action after setteled payment**
1) Successfully handle ´payment´ object JSON, extracting necessary details.
2) Generate a structured receipt based on the extracted payment information.
3) Display a "Print Receipt" button or pop up on the TPOS screen after a payment is processed. (+ add print button in "last sales" as well)
4) Print the receipt when the "Print Receipt" button is clicked.


![print_3](https://github.com/DoktorShift/tpos_receipt_print/assets/106493492/9a99ec7a-ba07-4a45-8cc8-40599459c507)

**Steps to archive Bounty**
1. Payment JSON Handling:
   -  Extract the 'payment' object from the received JSON

2. Printable Receipt Generation:
   -  Create a visually appealing receipt format that includes relevant payment details. [Could be a source](https://github.com/lnbits/tpos-receipt-printer/blob/main/firmware/src/print.h#L214)

3. Implement functionality to detect if the device has an available printer.
   -  Provide alternative options if no printer is detected.

4. UI Enhancement:
   -  Modify the TPOS screen to display a "Print Receipt" button after the payment is successfully processed. (see above screenshot left)
   -  Modify TPoS receipt "last payments" to print receipt even after the payment process is finished. (see above Screenshot right)

## Archivment example


https://github.com/DoktorShift/tpos_receipt_print/assets/106493492/e926a0dd-4adc-45e4-bc39-84ee11a668c3




## Contribute:
You want to contribute but lack of skillz? You can [Donate](https://timecatcher.lnbits.de/tipjar/31) to enhance the bounty and make it attractive for developer to code this.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Live Wallet Balance</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
        }
        .balance {
            background-color: #fff;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
    </style>
</head>
<body>
    <div class="balance">
        <h1>Wallet Balance: <span id="walletBalance">Loading...</span></h1>
    </div>

    <script>
        async function fetchWalletBalance() {
            try {
                const response = await fetch('/api/walletBalance');
                if (!response.ok) {
                    throw new Error('Network response was not ok');
                }
                const data = await response.json();
                document.getElementById('walletBalance').textContent = data.balance + ' sats';
            } catch (error) {
                console.error('Error fetching wallet balance:', error);
                document.getElementById('walletBalance').textContent = 'Error fetching balance';
            }
        }

        // Fetch the wallet balance initially
        fetchWalletBalance();

        // Set an interval to fetch the wallet balance every 10 seconds
        setInterval(fetchWalletBalance, 10000);
    </script>
</body>
</html>


## Restrictions
Do not add dependencies, LNbits has plenty of dependencies you can use.
