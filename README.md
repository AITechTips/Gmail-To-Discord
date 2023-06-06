# Gmail to Discord Webhook Integration

This repository contains a Google Apps Script that retrieves emails from your Gmail inbox and sends them to a Discord webhook in chunks. It is designed to run as a periodic task using Google's time-based triggers.

## Usage

1. Open the Google Apps Script editor for your Gmail account.
2. Create a new script file and copy-paste the code from [main.gs](main.gs) into it.
3. Customize the `webhookUrl` variable with your Discord webhook URL.
4. Save the script file.
5. Run the `createTrigger` function once to set up the time-based trigger for the `sendEmailsToWebhook` function.
6. The `sendEmailsToWebhook` function will be triggered every minute (you can adjust this frequency by modifying the `.everyMinutes()` parameter).
7. The script will retrieve emails from your Gmail inbox, split the content into chunks, and send each chunk to the Discord webhook.

## Code Explanation

The code consists of several functions:

- `sendEmailsToWebhook()`: This is the main function that retrieves emails from the Gmail inbox, splits the content into chunks, and sends them to the Discord webhook.
- `getEmailContent(message)`: This function extracts the subject, sender, and body of an email and returns them as a formatted string.
- `splitIntoChunks(content, maxLength)`: This function splits a string into chunks of a specified maximum length.
- `sendToWebhook(webhookUrl, message)`: This function sends a message to the Discord webhook using a POST request.
- `createTrigger()`: This function sets up a time-based trigger to run the `sendEmailsToWebhook` function periodically.

Feel free to modify the code to fit your specific requirements and customize the functionality according to your needs.

## Contributions

Contributions to this project are welcome! If you find any issues or have suggestions for improvements, please feel free to open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).

