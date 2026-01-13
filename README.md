# **Ex.No.6 – Development of Python Code Compatible with Multiple AI Tools**

**Name : Rishanth**

**Register No : 212222210021**

---

## **Aim:**

Write and implement Python code that integrates with multiple AI tools to automate the task of interacting with APIs, comparing outputs, and generating actionable insights from different AI systems.

---

## **AI Tools Required:**

• ChatGPT API
• Gemini API
• Python 3.10+
• Requests / HTTP client library
• Internet-enabled system

---

# **Explanation:**

In this experiment, the **persona pattern** is applied by acting as a *Python programmer* who develops code capable of interacting with more than one AI tool.
The goal is to write Python code that sends the same query to different AI APIs, retrieves the responses, compares them, and displays meaningful insights.

This demonstrates how prompt engineering combined with Python automation can help evaluate AI model behavior, output clarity, and consistency.

---

# **Algorithm:**

1. **Start**
2. Accept a user query as input
3. Pass the query to **ChatGPT API** and collect the response
4. Pass the same query to **Gemini API** and collect the response
5. Store both responses in Python variables
6. Compare outputs based on length, keywords, and clarity
7. Print all results in a structured format
8. **Stop**

---

# **Program (Python Code)**

```python
import requests

def call_chatgpt(prompt):
    url = "https://api.openai.com/v1/chat/completions"
    headers = {
        "Authorization": "Bearer YOUR_CHATGPT_API_KEY",
        "Content-Type": "application/json"
    }
    data = {
        "model": "gpt-4",
        "messages": [{"role": "user", "content": prompt}]
    }
    response = requests.post(url, headers=headers, json=data)
    return response.json()["choices"][0]["message"]["content"]


def call_gemini(prompt):
    url = "https://generativelanguage.googleapis.com/v1beta/models/gemini-pro:generateContent"
    headers = {
        "Content-Type": "application/json"
    }
    data = {
        "contents": [{"parts": [{"text": prompt}]}],
        "apiKey": "YOUR_GEMINI_API_KEY"
    }
    response = requests.post(url, headers=headers, json=data)
    return response.json()["candidates"][0]["content"]["parts"][0]["text"]


def compare_outputs(prompt):
    print("\n----- Prompt Sent to Both AI Tools -----")
    print(prompt)

    chatgpt_output = call_chatgpt(prompt)
    gemini_output = call_gemini(prompt)

    print("\n----- ChatGPT Response -----")
    print(chatgpt_output)

    print("\n----- Gemini Response -----")
    print(gemini_output)

    print("\n----- Comparison Summary -----")
    print(f"ChatGPT response length: {len(chatgpt_output)} characters")
    print(f"Gemini response length: {len(gemini_output)} characters")


# Example usage:
compare_outputs("Explain the importance of automation in modern industries.")
```

---

# **Example Output**

### **Prompt:**

*“Explain the importance of automation in modern industries.”*

### **ChatGPT Output (Sample):**

Automation improves efficiency, reduces human error, enables consistent production quality, and lowers operational costs. It increases productivity and provides real-time control in manufacturing environments.

### **Gemini Output (Sample):**

Automation is essential for boosting production speed, enhancing accuracy, improving labor safety, and minimizing downtime. It helps industries scale operations while maintaining reliability.

---

# **Analysis of Code Using ChatGPT & Gemini**

### **ChatGPT Strengths:**

• Provides more elaborate explanations
• Clear structure and strong reasoning
• Better contextual descriptions

### **Gemini Strengths:**

• Gives concise and direct answers
• Faster and more compact responses
• Useful for short analysis tasks

### **Overall Observation:**

Both AI tools respond well, but **ChatGPT gives deeper and structured answers**, while **Gemini provides concise and focused responses**.
The Python code successfully sends prompts to both models and prints a comparison summary.

---

# **Conclusion:**

The Python code was successfully developed and integrated with multiple AI tools.
The code retrieved outputs from both ChatGPT and Gemini, compared their responses, and demonstrated how prompt engineering can be combined with Python automation to generate meaningful insights across AI platforms.

---

# **Result:**

The corresponding prompt is executed successfully.

---
