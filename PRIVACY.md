# Privacy Policy — pgwp-mod-notifier

_Effective date: 23 November 2026_

pgwp-mod-notifier ("the app") is a private moderation tool built for the
moderators of the PGWP subreddit. It sends them an alert whenever a new post or
comment appears there. It is not offered to other communities: it is built to do
nothing in any other subreddit, apart from the developer's own small test
subreddit. This policy explains what information the app handles,
where it goes, and how long it is kept.

The app is run by Reddit user u/mygrationmod ("we", "us"). Questions: send a Reddit message to u/mygrationmod.

## In short

- The app reads **new posts and comments** in the PGWP subreddit (and the developer's own test subreddit), and forwards a short alert to the moderators' **Slack** channels (one for posts, one for comments).
- When a post or comment is **deleted on Reddit**, the app deletes its Slack alert too.
- It does **not** read private messages, Modmail conversations, or any account details beyond a username.
- It does **not** sell or share data, show ads, run analytics, or use data to train AI models.
- We do not run our own servers or databases. The app runs on Reddit's Developer Platform.

## Information the app handles

| Information | Source | Why |
| --- | --- | --- |
| For each new **post**: title, author username, subreddit name, link, and the post text (or the link it points to) | Reddit, when the post is created | To tell moderators a post was made. Only the title, author and link are included in the Slack alert. |
| For each new **comment**: author username, subreddit name, the title of the post it was left on, link, and comment text (clipped to 1,500 characters) | Reddit, when the comment is created | To tell moderators a comment was made. The Slack alert includes the author, the comment text and the link. |
| The Slack channel and message timestamp of each alert, filed under the post or comment's ID | Slack, when the alert is posted | So the alert can be deleted from Slack if the post or comment is deleted on Reddit. Contains no username or text. |
| App settings: which alert types are on, a list of usernames to ignore, the two Slack channel IDs, and optionally a Reddit username to send private messages to | The moderator, on the app's settings page | To apply the moderator's choices. |
| The Slack bot token | The app's developer | To post and delete alerts in the developer's Slack workspace. Stored as a secret on Reddit's platform. |
| Content IDs (for example `t1_abc123`) | Reddit | To avoid sending the same alert twice if Reddit repeats an event. |

The app only handles content posted in the PGWP subreddit and the developer's
own test subreddit; anywhere else it is built to do nothing. It does not ask redditors for any information and does not collect
email addresses, passwords, locations, or device details.

## How the information is used

Only to send alerts to the moderators who set the app up, to remove those
alerts when the content is deleted, and to apply their settings (for example
skipping posts from AutoModerator). We do not use it for any other purpose.

## Where the information goes

- **Slack.** Alerts are posted by a Slack app (a bot) that the app's developer installs in their own Slack workspace, to two channels there: one for posts and one for comments. Once a message is in Slack, it is governed by that workspace's settings and by [Slack's own policies](https://slack.com/trust/privacy/privacy-policy). Whoever can see those channels can see the alerts, so they should be limited to moderators.
- **Reddit.** If a moderator turns them on, alerts can also be sent as a Reddit private message or as a Modmail notification. These stay inside Reddit.
- **Nobody else.** We do not sell, license, or share this information with anyone, and we do not combine it with other data.

## Storage and retention

The app stores data only in the storage Reddit provides to each installation of
the app. We do not copy it anywhere else.

- **Duplicate-prevention markers** (content IDs only, no usernames or text) are deleted automatically after 24 hours.
- **Slack message references** (channel and timestamp, filed under the post or comment ID) are kept for as long as the post or comment exists on Reddit, and deleted when Reddit reports it deleted.
- **Digest queue** (only when a moderator turns on the private message / Modmail digest): alerts wait in the queue until the next digest is sent, normally within about five minutes, and are removed once it has been delivered or the content is deleted. The queue holds at most 500 alerts; if more arrive while delivery is failing, the oldest are dropped. Slack alerts never wait in the queue.
- **Settings and the Slack token** are kept for as long as the app is installed.
- **Logs** contain post or comment IDs and error messages, not the text of posts or comments.
- **Messages in Slack** are kept according to the workspace's own retention settings, until the app (or someone) deletes them.

## Content deleted on Reddit

When Reddit tells the app that a post or comment was deleted, the app deletes
the matching alert from Slack and removes any copy still waiting in the digest
queue. Some limits:

- If Slack cannot be reached or refuses the deletion at that moment, the alert may stay in Slack until someone deletes it. Contact us and we will remove it.
- Reddit private messages and Modmail notifications, if a moderator turned them on, are not recalled by the app.
- The app can only act on deletions that Reddit reports to it.
- Slack may keep its own copies, such as exports or backups, under the workspace's settings.

## Children

Reddit requires users to be at least 13 years old, and the app does not
knowingly handle information from anyone under 13.

## Security

The app runs on Reddit's platform. The Slack token is stored as a secret and is
masked if it ever appears in an error message or log. No method of
transmission or storage is perfectly secure, so we cannot guarantee absolute
security.

## Your choices

- **Moderators** can turn alert types and extra channels on or off in the app settings, or uninstall the app at any time, which stops it receiving content from the subreddit.
- **Redditors** whose content appears in an alert can delete the post or comment on Reddit (the alert is then removed), or ask us to delete the alert using the contact below.

## Changes

If we change this policy we will update the date at the top. Material changes
will be described in the app's README.

## Contact

Send a Reddit message to [u/mygrationmod](https://www.reddit.com/user/mygrationmod). If you are asking for an alert to be removed, include a link to the post or comment.
