# Monitoring and alerting

Validators expose metrics on the port number specified by the argument `--metrics`. Port `9090` is the default, though any valid port can be chosen.

{% hint style="info" %}
If running as a Docker image, make sure to port-forward the metrics endpoint port. For, instance, to forward port 9090 on the local port 80, add the following flag to your `docker run` command: `-p 9090:80`
{% endhint %}

We also provide a mostly-ready-to-go Grafana dashboard to get you started, you can find the source and instructions for importing it under [tools/grafana](https://github.com/hyperlane-xyz/hyperlane-monorepo/tree/main/tools/grafana). If you want to use your own, the `hyperlane_latest_checkpoint` is the most critical metric in both the `phase="validator_observed"` and `phase="validator_processed"` dimension. It should gradually increase and the two should never really be out of sync.