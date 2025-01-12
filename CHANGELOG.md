## 7.3.2
  - Change `tls_certificate_password` type to `password` to protect from leaks in the logs [#54](https://github.com/logstash-plugins/logstash-integration-rabbitmq/pull/54)

## 7.3.1
  - DOCS: clarify the availability and cost of using the `metadata_enabled` option [#52](https://github.com/logstash-plugins/logstash-integration-rabbitmq/pull/52)

## 7.3.0
  - Refactor: logging improvements [#47](https://github.com/logstash-plugins/logstash-integration-rabbitmq/pull/47)
    * integrated MarchHare logging to be part of Logstash's log instead of using std-err
    * normalized logging format on (Ruby) errors

## 7.2.0
  - Remove ruby pipeline dependency. Starting from Logstash 8, Ruby execution engine is not available. All pipelines should use Java pipeline [#39](https://github.com/logstash-plugins/logstash-integration-rabbitmq/pull/39)

## 7.1.1
  - DOC:Replaced plugin_header file with plugin_header-integration file. ([#34](https://github.com/logstash-plugins/logstash-integration-rabbitmq/issues/34))

## 7.1.0
  - Added support in Output plugin for `sprintf` templates in values provided to `message_properties` ([#8](https://github.com/logstash-plugins/logstash-integration-rabbitmq/issues/8))
  - Added support for _extended_ metadata including raw payload to events generated by the Input Plugin [#13](https://github.com/logstash-plugins/logstash-integration-rabbitmq/issues/13)
  - Fixes an issue with custom port assignment, in which the custom port was not being applied when more than one host was supplied [#12](https://github.com/logstash-plugins/logstash-integration-rabbitmq/pull/12)
  - Fixes bug where attempting to read from undeclared exchange resulted in infinite retry loop ([#10](https://github.com/logstash-plugins/logstash-integration-rabbitmq/issues/10))
  - Fixes bug where failing to establish initial connection resulted in a pipeline that refused to shut down ([#11](https://github.com/logstash-plugins/logstash-integration-rabbitmq/issues/11))

## 7.0.3
  - Refactor: scope (and remove unused) java imports [#29](https://github.com/logstash-plugins/logstash-integration-rabbitmq/pull/29)

## 7.0.2
  - Fixes issue in Output where failure to register connection reovery hooks prevented the output from starting

## 7.0.1
  - Improves Input Plugin documentation to better align with upstream guidance [#4](https://github.com/logstash-plugins/logstash-integration-rabbitmq/pull/4)

## 7.0.0
  - Initial release of the RabbitMQ Integration Plugin, which combines
    previously-separate RabbitMQ plugins and shared dependencies into a single
    codebase; independent changelogs for previous versions can be found:
     - [RabbitMQ Input Plugin @6.0.3](https://github.com/logstash-plugins/logstash-input-rabbitmq/blob/v6.0.3/CHANGELOG.md)
     - [RabbitMQ Output Plugin @5.1.1](https://github.com/logstash-plugins/logstash-output-rabbitmq/blob/v5.1.1/CHANGELOG.md)
  - Absorbed connection mixin dependency; independent changelog history for
    the mixin can be found here: [RabbitMQ Connection Mixin @5.1.0](https://github.com/logstash-plugins/logstash-mixin-rabbitmq_connection/blob/v5.1.0/CHANGELOG.md)
  - In the Output plugin, when a connection is flagged as blocked, back-pressure is now propagated to the pipeline until the connection is either unblocked or recovered, preventing runaway writes to blocked connections ([#1](https://github.com/logstash-plugins/logstash-integration-rabbitmq/pull/1))
