# Linux Web Server Troubleshooting

This reference checklist supports the AWS/Linux web-server lab. It is not a verbatim transcript of every command in the video.

## 1. Check AWS Connectivity

- Confirm that the EC2 instance is running.
- Check its instance status checks.
- Confirm its current public IPv4 address.
- Verify the subnet's route-table association.
- Confirm the default route points to the internet gateway.
- Check that the security group permits the intended HTTP traffic.

## 2. Check Nginx

Inspect the service:

```bash
sudo systemctl status nginx --no-pager
```

Validate the Nginx configuration:

```bash
sudo nginx -t
```

Review recent service logs:

```bash
sudo journalctl -u nginx -n 50 --no-pager
```

## 3. Test HTTP Locally

```bash
curl -I http://localhost
```

A local HTTP response helps distinguish a web-service problem from an external connectivity problem. Inspect the returned status code rather than assuming every response means success.

## 4. Retest Externally

Open the website using the instance's current public address.

Compare the browser result with the local HTTP test and service logs.

## 5. Review Monitoring

Check the CloudWatch agent and reported server metrics.

Missing metrics can indicate an agent configuration, permissions, or connectivity issue—not necessarily a failed web server.

## Recovery Verification

After applying a correction:

- Recheck service status and configuration.
- Repeat the local HTTP test.
- Repeat the external browser test.
- Document the symptom, evidence, correction, and result.

Do not include credentials, private identifiers, or real client data in troubleshooting evidence.
