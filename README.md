# Slack Status Manager

Sets status of slack workspaces based on whether or not a zoom call is open.

## Configuration & Installation

* Create a [Slack App](https://api.slack.com/apps)
* Configure User Token Scopes:
  * `users.profile.write`

You will need the access token from the "OAuth & Permissions" section of your Slack App.

### Configuration

Create a JSON, TOML, YAML, HCL, envfile or Java properties config file, in either your $HOME directory or the directory you're running the compiled go binary in (ie repo root). The file should be prefixed with `.zoom-slack-status`. For example, `~/.zoom-slack-status.yml` if you're creating a YAML file. (See [spf13/viper](https://github.com/spf13/viper) for more details)

```yaml
accounts:
  - name: My slack workspace
    token: xoxp-123456890abcdefghijklmnopqrstuvwxyz
    # Optional
    # meetingStatus:
    #   status_text: "In a meeting"
    #   status_emoji: ":zoom:"
    # noMeetingStatus:
    #   status_text: "I'm available"
    #   status_emoji: ":facepalm:"

# interval for how often to check if a Zoom meeting is in progress (default: 60s)
interval: "60s"
```

## Download

Download the latest release from <https://github.com/caitlinelfring/zoom-slack-status/releases>.

1. Download the `.tar.gz` file from releases.
2. Double-click on the downloaded file to extract `zoom-slack-status.app` to your `/Applications` folder.
3. Copy `zoom-slack-status.app` to your `/Applications` folder.
4. Launch the app from `/Applications` in your Finder.

### Developing

Run with the go toolchain with `go run main.go`. Or `go build . && ./zoom-slack-status`.

### Build "Mac App"

1. Build the app with `make build`
2. Copy `dist/zoom-slack-status.app` to your `/Applications` folder.
3. Launch the app from `/Applications` in your Finder
