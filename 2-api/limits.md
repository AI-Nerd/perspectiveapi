[Perspective API documentation](../README.md) > [API Reference Docs](README.md) > **Limits**

# Limits and errors

The Perspective API uses limits and quotas to protect the system from receiving
more data than it can handle, and to ensure equitable distribution of the
system resources. These limits and quotas are subject to change.

You may encounter an error if your request exceeds the limit.

## Quota limit

By default, we set a quota limit to an average of 1 query per second (QPS) for
all Perspective projects. This limit should be enough for testing the API and
for working in developer environments.

Check your quota limits by going to
[your Google Cloud project's Perspective API page](https://console.cloud.google.com/apis/api/commentanalyzer.googleapis.com/quotas),
and check your project's quota usage at
[the cloud console quota usage page](https://console.cloud.google.com/iam-admin/quotas).

If you're running a production website, you may need to
[request a quota increase](https://support.perspectiveapi.com/s/request-quota-increase).

## Character limit for requests

You may encounter the following error:

```
Comment text too long.
```

The maximum text size per request is 3000 bytes. One character does not
necessarily equal one byte, as different characters have different encodings.
For example, a UTF-8 Unicode character has an encoding between 1 byte and 4
bytes.

[Read the W3C guide on character encoding](https://www.w3.org/International/questions/qa-what-is-encoding).


## Other errors

Here are some examples of other errors you may encounter.

#### Comment is empty

```
Comment must be non-empty.
```

Comments queried must contain content.

#### Languages not supported

```
Attribute <attr_name> does not support request languages: <lang1, lang2>
```

The request for `<attr_name>` in `<lang1>` and `<lang2>` is not possible
because we do not yet support it. Read more about the
[available languages](models.md#specifying-language).

#### Unknown language

```
Unable to detect language
```

We are unable to detect what language is being used in the comment. Read more
about the [available languages](models.md#specifying-language).

## All reference materials

Read more about the Perspective API and how to use it.

* [Key concepts](key-concepts.md)
* [Attributes](models.md)
   * [Model cards](model-cards/README.md)
* [Methods](methods.md)
   * [Scoring comments](methods.md#scoring-comments-analyzecomment)
   * [Sending feedback](methods.md#sending-feedback-suggestcommentscore)
* [API client libraries](clients.md)
* **Limits and errors**
