from dotenv import load_dotenv
from twilio.rest import Client
import os


load_dotenv()

#Creds
account_sid = os.getenv("account_sid")
auth_token = os.getenv("auth_token")
twilio_number = os.getenv("twilio_number")
target_number = os.getenv("target_number")

client = Client(account_sid, auth_token)

def send_text_message(message):
    try:
        message = client.messages.create(
            body=message,
            from_=twilio_number,
            to=target_number
        )
        print(f"Message sent to {target_number}: {message.sid}")
    except Exception as e:
        print(f"Failed to send message: {e}")

if __name__ == "__main__":
    message = "Active fire is detected in your area. Please find your nearest exit, evacuate calmly, and follow instructions from the authorities"
    send_text_message(message)
