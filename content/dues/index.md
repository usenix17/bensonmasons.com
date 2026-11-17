---
title: 2026 Dues
menu:
  main:
    weight: 2
---

Dues season is here and [online payment](#dues-form) is available! 

**OR You can pay through the [Grand View Member Portal](https://ne.grandview.systems/)**

**Dues for 2026 are $120** and are explained below:

| Description                                                      | Amount      |
|------------------------------------------------------------------|-------------|
| **Grand Lodge Per Capita Tax (Breakout Below)**                  | $37.00      |
|   - Grand Lodge of NE General Fund                               | $31.00      |
|   - Nebraska Masonic Home                                        | $2.50       |
|   - Masonic-Eastern Star Home for Children                       | $1.50       |
|   - George Washington Masonic Memorial                           | $1.50       |
|   - Masonic Education Newsletter                                 | $0.50       |
| **Grand Lodge Assessments (Breakout Below)**                     | $3.00       |
|   - Child Identification Program (CHIP)                          | $1.50       |
|   - Nebraska Job’s Daughters                                     | $0.50       |
|   - International Order of Rainbow Girls                         | $0.50       |
|   - Nebraska DeMolay                                             | $0.50       |
| **Mercer Lodge Dues**                                            | $80.00      |
|   (Optional) Donation to offset online payment costs             | $5.00       |
|                                                                  |             |
| **DUES TOTAL (without donation to offset online payment costs)** | **$120.00** |


## Millennium Fund

Mercer Lodge has a Millennium Fund used for assisting in the payment of dues for Brethren of Mercer Lodge who are unable to meet their dues obligation.

The Masonic principles of brotherly love, relief, and truth should not allow a member to be dropped from the rolls for nonpayment of dues if a Brother genuinely wishes to remain a Mason. Should funds be remaining at the end of the year, they may be used to augment charitable giving or fundraising by the lodge. Should you desire to contribute to the fund, you have the option of adding an additional amount to your check or online dues payment.

## Ways to Pay

#### By Check

Checks should be made out to:  
 **John J. Mercer Lodge No. 290**

Checks can be mailed to:  
John J. Mercer Lodge  
5903 Maple St.  
Omaha, NE 68104

#### Online

Mercer Lodge uses PayPal to receive online payments. 

  * **PayPal _does_ charge the Lodge for each transaction**. We ask (although optional) that a Brother help contribute to offsetting these costs ($5) if paying online. Due to PayPal terms, we cannot &#8220;impose&#8221; any type of fee but we can give you the option to choose for yourself.

Please fill out the form below to and click the &#8220;Pay Dues&#8221; button to initiate the online payment process. Once that &#8220;Pay Dues&#8221; button is clicked, you will be presented with buttons for payment options.

For any issues with submitting dues online, please send an email to info@bensonmasons.com and someone will get back to you.

{{< rawhtml >}}
<h2 id="dues-form">Online Payment Form</h2>
<script src="https://www.paypal.com/sdk/js?client-id=ASJRpc7ZXZWsMgK93sIyuYtBUfeqqL3zSRdMaqcsQp84sVAAOtIXbE9Xe2ymZpiacMw7Kz9G7S8VksKJ"> // Required. Replace SB_CLIENT_ID with your sandbox client ID.
</script>
<script>
    var LODGE_DUES_AMOUNT = 120.00;
    var DIGITAL_PAYMENT_CONTRIBUTION_AMOUNT = 5.00;

    function setPayDuesButtonVisibility(isVisible) {
        var payDuesButton = document.querySelector('#submit-dues-form');
        if (isVisible) {
            payDuesButton.style.display = 'inline-block';
            return;
        }
        payDuesButton.style.display = 'none';
    }

    function getAmountBeingContributedToMillenniumFund() {
        var milleniumFundAmount = document.querySelector('#millenniumFundAmount').value;
        if (milleniumFundAmount > 0) {
            return parseFloat(milleniumFundAmount);
        }
        return 0.00;
    }

    function getAmountBeingContributedToDigitalPaymentFund() {
        var contributingToDigitalPaymentFund = document.querySelector('#digitalPaymentDonation').value;
        if (contributingToDigitalPaymentFund === 'yes') {
            return DIGITAL_PAYMENT_CONTRIBUTION_AMOUNT;
        }
        return 0.00;
    }

    function getDuesTotal() {
        return (LODGE_DUES_AMOUNT + parseFloat(getAmountBeingContributedToMillenniumFund()) + getAmountBeingContributedToDigitalPaymentFund()).toFixed(2);
    }

    function getFirstName() {
        return document.querySelector('#brothersFirstName').value;
    }

    function getLastName() {
        return document.querySelector('#brothersLastName').value;
    }

    function getFullName() {
        return getFirstName() + " " + getLastName();
    }

    function validateDuesForm() {
        if (getLastName().length < 2 || getFirstName().length < 2) {
            alert('You must enter first AND last name so that we know who to mail the dues card to.');
            return false;
        }
        if (getAmountBeingContributedToMillenniumFund() < 0) {
            alert('You can\'t enter a negative amount for Millennium Fund');
            return false;
        }
        return true;
    }

    function getDateAsString() {
        var date = new Date();
        var dateAsString = "";
        var year = date.getFullYear().toString();
        var month = (date.getMonth() + 1).toString();
        var day = date.getDate().toString();
        if (month.length === 1) {
            month = "0" + month;
        }
        if (day.length === 1) {
            day = "0" + day;
        }
        return year + month + day;
    }

    function generateReferenceId(itemType, fullName) {
        var date = getDateAsString();
        var condensedName = fullName.replace(/[^A-Za-z]/g, '');
        return date + '_' + itemType + '_' + condensedName;
    }

    function getItems() {
        var items = [];
        var millenniumFundAmount = getAmountBeingContributedToMillenniumFund();
        var digitalPaymentFundAmount = getAmountBeingContributedToDigitalPaymentFund();
        var fullName = getFullName();

        items.push({
            unit_amount: { currency_code: 'USD', value: LODGE_DUES_AMOUNT },
            name: "John J. Mercer Lodge Dues - 2026 (" + fullName + ")",
            description: "John J. Mercer Lodge Dues - 2026 (" + fullName + ")",
            quantity: 1
        });

        if (millenniumFundAmount > 0.00) {
            items.push({
                unit_amount: { currency_code: 'USD', value: millenniumFundAmount },
                name: "John J. Mercer Millennium Fund Donation - 2026 (" + fullName + ")",
                description: "John J. Mercer Millennium Fund Donation - 2026 (" + fullName + ")",
                quantity: 1
            });
        }

        if (digitalPaymentFundAmount > 0.00) {
            items.push({
                unit_amount: { currency_code: 'USD', value: digitalPaymentFundAmount },
                name: "John J. Mercer DigitalPay Fund Donation - 2026 (" + fullName + ")",
                description: "John J. Mercer DigitalPay Fund Donation - 2026 (" + fullName + ")",
                quantity: 1
            });
        }

        return items;
    }

    function resetPPButtonContainer() {
        document.querySelector('#paypal-button-container').innerHTML = '';
    }

    function resetForm() {
        document.querySelector('.dues-form').reset();
        recalculateTotalDues();
    }

    function scrollToTop() {
        document.body.scrollTop = 0;
        document.documentElement.scrollTop = 0;
    }

    function recalculateTotalDues() {
        document.querySelector('.dues-generated-total').innerHTML = getDuesTotal();
    }

    function submitDues() {
        if (validateDuesForm()) {
            paypal.Buttons({
                createOrder: function (data, actions) {
                    return actions.order.create({
                        purchase_units: [{
                            amount: {
                                value: getDuesTotal(),
                                breakdown: {
                                    item_total: { currency_code: "USD", value: getDuesTotal() },
                                    shipping: { currency_code: "USD", value: "0" },
                                    tax_total: { currency_code: "USD", value: "0" },
                                    discount: { currency_code: "USD", value: "0" }
                                }
                            },
                            description: "John J. Mercer Lodge Dues Payment (2026)",
                            items: getItems()
                        }]
                    });
                },
                onApprove: function (data, actions) {
                    console.log("PPT Data", data);
                    return actions.order.capture().then(function (orderDetails) {
                        console.log(orderDetails);
                        var paymentConfirmationDiv = document.querySelector('#payment-confirmation');
                        paymentConfirmationDiv.innerText = 'Success! Your payment to John J. Mercer Lodge has been completed ' +
                            'successfully. PayPal will send you a confirmation email to the address provided. ' +
                            'Please print this page or take note of the following reference number should ' +
                            'you need it in the future: \n\n  ' +
                            'Reference ID: ' + orderDetails.purchase_units[0].payments.captures[0].id + '\n\n' +
                            'If you do not receive your dues card within 14 days, please contact the Lodge Secretary.';
                        scrollToTop();
                        paymentConfirmationDiv.style.display = 'block';
                        resetForm();
                        resetPPButtonContainer();
                        setPayDuesButtonVisibility(true);
                    });
                },
            }).render('#paypal-button-container');
            setPayDuesButtonVisibility(false);
        }
    }

    window.onload = (event) => {
        var formFields = document.querySelectorAll('.dues-form-field');
        formFields.forEach(function (field) {
            field.addEventListener('change', function () {
                recalculateTotalDues();
                resetPPButtonContainer();
                setPayDuesButtonVisibility(true);
            });
        });

        document.querySelector('#submit-dues-form').addEventListener('click', function () {
            submitDues();
        });
    };
</script>

<form class="dues-form">
    <ul class="flex-outer">
            <br>
            <label for="brothersFirstName">Brother's First Name</label>
            <input type="text" id="brothersFirstName" name="brothersFirstName" placeholder="Enter your first name here" class="dues-form-field">
            <br>
            <label for="brothersLastName">Brother's Last Name</label>
            <input type="text" id="brothersLastName" name="brothersLastName" placeholder="Enter your last name here" class="dues-form-field">
            <br>
            <label for="digitalPaymentDonation">I would like to contribute to offset digital payments efforts</label>
            <select name="digitalPaymentDonation" id="digitalPaymentDonation" class="dues-form-field">
                <option value="yes" selected="">Yes</option>
                <option value="no">No</option>
            </select>
            <br>
            <label for="millenniumFundAmount">
                I would like to contribute the following amount the Millennium Fund to help brothers who are only able to pay partial or no dues this year (in dollars)
            </label>
            <input type="number" id="millenniumFundAmount" name="millenniumFundAmount" placeholder="0.00" class="dues-form-field">
            <br>
            Checkout Total:&nbsp;&nbsp;&nbsp;$<span class="dues-generated-total">120.00</span>
            <br>
            <button type="button" id="submit-dues-form">Pay Dues</button>
            <div id="paypal-button-container"></div>
    </ul>
</form>
{{< /rawhtml >}}
