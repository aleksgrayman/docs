---
title: "How to configure an {{ KF }} target endpoint in {{ data-transfer-full-name }}"
description: "In this tutorial, you will learn how to set up an {{ KF }} target endpoint in {{ data-transfer-full-name }}."
---

# Configuring an {{ KF }} target endpoint

When [creating](../index.md#create) or [editing](../index.md#update) an endpoint, you can define:

* [{{ mkf-full-name }} cluster](#managed-service) connection or [custom installation](#on-premise) settings and [serialization settings](#serializer), including those based on {{ compute-full-name }} VMs. These are required parameters.
* [Apache Kafka topic settings](#kafka-settings).

## {{ mkf-name }} cluster {#managed-service}


{% note warning %}

To create or edit an endpoint of a managed database, you need to have the [`{{ roles.mkf.viewer }}` role](../../../../managed-kafka/security/index.md#mkf-viewer) or the [`viewer` primitive role](../../../../iam/concepts/access-control/roles.md#viewer) assigned to the folder where this managed database cluster resides.

{% endnote %}


Connecting to the database with the cluster ID specified in {{ yandex-cloud }}.

{% list tabs group=instructions %}

- Management console {#console}

   {% include [Managed Kafka UI](../../../../_includes/data-transfer/necessary-settings/ui/managed-kafka-target.md) %}

{% endlist %}

## Custom installation {#on-premise}

Connecting to the database with explicitly specified network addresses.

{% list tabs group=instructions %}

- Management console {#console}

   {% include [On premise Kafka UI](../../../../_includes/data-transfer/necessary-settings/ui/on-premise-kafka-target.md) %}

{% endlist %}

## Topic settings {{ KF }} {#kafka-settings}

{% list tabs group=instructions %}

- Management console {#console}

   {% include [On premise Kafka UI](../../../../_includes/data-transfer/kafka-topic.md) %}

   {{ data-transfer-full-name }} supports CDC for transfers from {{ PG }}, {{ MY }}, and {{ ydb-short-name }} databases to {{ KF }} and {{ yds-full-name }}. Data is sent to the target in Debezium format. For more information about CDC mode, see [Change data capture](../../../concepts/cdc.md).

   {% include [CDC-YDB](../../../../_includes/data-transfer/note-ydb-cdc.md) %}

   * **{{ ui-key.yc-data-transfer.data-transfer.console.form.kafka.console.form.kafka.KafkaTargetTopic.save_tx_order.title }}**: Do not split an event stream into independent queues by table.

{% endlist %}

## {{ ui-key.yc-data-transfer.data-transfer.console.form.common.console.form.common.Serializer.serializer.title }} {#serializer}

{% list tabs group=instructions %}

- Management console {#console}

   {% include [serializer](../../../../_includes/data-transfer/serializer.md) %}

{% endlist %}
