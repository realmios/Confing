/*
 * Locket Gold Fixer for Stash
 */
let obj = JSON.parse($response.body);
let url = $request.url;

if (url.includes("getUserInfo") || url.includes("getUserByUsername") || url.includes("changeProfileInfo")) {
    if (obj.data) {
        obj.data.badge = "locket_gold"; 
        obj.data.is_gold = true;
    }
}

if (url.includes("getSubscriptionV2")) {
    obj.data = {
        "subscriptions": [{
            "expires_date": "2099-12-31T12:00:00Z",
            "purchase_date": "2024-01-01T12:00:00Z",
            "product_identifier": "locket_gold_yearly"
        }],
        "entitlements": {
            "gold": {
                "expires_date": "2099-12-31T12:00:00Z",
                "product_identifier": "locket_gold_yearly"
            }
        }
    };
}

$done({ body: JSON.stringify(obj) });
