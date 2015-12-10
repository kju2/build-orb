#buildbulb

A server application to turn a LIFX light bulb into an extreme feedback device for multiple Jenkins projects.

**Note:** Your LIFX light bulb must have the label _BuildBulb_ for this script to work.

## Install

```shell
go get -u github.com/kju2/buildbulb
```

The buildbulb command will be available at ${GOPATH}/bin/.

## Usage

```shell
./buildbulb --port=8080 --jobsFilePath=/path/to/load/and/persist/jobs
```

Command line parameters to configure the application are work in progress.

## Jenkins Setup

- Install the [https://wiki.jenkins-ci.org/display/JENKINS/Notification+Plugin](Jenkins Notification Plugin).
- Configure Jenkins Notification Plugin to send the build status as JSON objects over HTTP the the server, e.g.
  - Format: JSON
  - Protocol: HTTP
  - Event: Finalized
  - URL: http://serverip:port/notify
- Build the job.

##Dependencies

- Go 1.4.+
- LIFX bulb (http://www.lifx.com/)

