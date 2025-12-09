---
title : "Testing"
weight : 5
chapter : false
pre : " <b> 5.5. </b> "
---

## Test the API with Thunder Client (VS Code)

After integrating API Gateway with Lambda, you have an HTTP endpoint ready for testing.  
In this step, you’ll use **Thunder Client** — a popular VS Code extension — to send requests and inspect responses.

---

## 🔹 Step 1 — Get the Invoke URL from API Gateway

In AWS API Gateway:

1. Open the **API Gateway** service.  
2. Select the API you created, e.g., `bedrock-chatbot-api`.  
3. In the left menu, choose **Deploy → Stages**.  
4. Click the **$default** stage.  
5. In **Stage details**, copy the **Invoke URL**.

![h1](/images/5-Workshop/5.5-h1.png)
![h3](/images/5-Workshop/5.5-h3.png)

Copy the **Invoke URL**, for example:

```
https://v8p3h9umxg.execute-api.ap-southeast-1.amazonaws.com
```

Next, append the route path you configured, e.g., `/chat`.

👉 The full endpoint will be:

```
https://v8p3h9umxg.execute-api.ap-southeast-1.amazonaws.com/chat
```

---

## 🔹 Step 2 — Install and open Thunder Client in VS Code

1. Open **VS Code**.  
2. Go to the **Extensions** tab.  
3. Search for **Thunder Client** and click **Install**.  
4. After installation, the **Thunder Client** icon appears in the sidebar.  
5. Click the icon and choose **New Request**.  
6. Select the **POST** method.  
7. Paste the endpoint into the URL box:

```
https://v8p3h9umxg.execute-api.ap-southeast-1.amazonaws.com/chat
```

---

## 🔹 Step 3 — Send JSON body and check the response

1. Choose the **Body → JSON** tab.  
2. Enter:

```json
{
  "question": "Amazon Bedrock là gì?"
}
```

Click **Send** to issue the request.

![h2](/images/5-Workshop/5.5-h2.png)

If everything is wired correctly, you should get a response like:

```json
{
  "answer": "Amazon Bedrock is a fully managed service..."
}
```

This confirms:

- API Gateway received the request successfully  
- Lambda ran correctly and called Bedrock  
- The system returned the expected result  

---

## 🔧 Troubleshooting

- **403 / AccessDeniedException** → Check the Lambda IAM role  
- **500 Internal Error** → Inspect CloudWatch Logs  
- **Missing 'question' field** → Validate the JSON body  
- **Timeout** → Increase Lambda timeout to 10–20 seconds  

---

## ✔ Conclusion

You’ve successfully tested the end‑to‑end pipeline:

**Client → API Gateway → Lambda → Bedrock → AI Response**

You’ve completed the testing portion of the workshop.
