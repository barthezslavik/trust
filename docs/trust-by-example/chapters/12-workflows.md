# 12. Workflows

Workflows are the primary execution unit in Trust.

Unlike traditional functions:

* workflows are durable,
* resumable,
* replayable,
* causally observable.

A workflow describes coordinated execution over time.

```trust id="ql9j6k"
workflow LeadPipeline {
  step search_leads()
  step scrape_websites()
  step score_companies()
  step save_to_crm()
}
```

Workflows may:

* pause,
* retry,
* wait for events,
* survive crashes,
* span multiple machines.

Each workflow execution has:

* workflow id,
* execution history,
* state graph,
* audit trail,
* causality lineage.

