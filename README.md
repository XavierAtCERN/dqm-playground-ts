# DQM Playground - Time Serie Analysis

This repository is an addition to the [website](https://github.com/CMSTrackerDPG/MLplayground), [CLI](https://github.com/XavierAtCERN/dqm-playground-cli), and [data analysis framework](https://github.com/XavierAtCERN/dqm-playground-ds) of the DQM Playground intiative. The goal is to move from representation based (PCA, [NMF](https://github.com/anushree85/ML4DQM_NMF1D), [autoencoders](https://github.com/CMSTrackerDPG/ML4DQMDC-PixelAE)) to time serie based monitoring / anomaly detection.

## Initial strategy

The goal of this project is twofold. First, check whether time serie analysis could help monitoring the Tracker. Second, test the modularity of the DQM Playground website by adding a new input to the monitoring (namely L1 and HLT rates) as a new application.

In order to do so, a preliminary approach could be the following:
- extract 2018 rates of L1/HLT using OMS API
- study the evolution of rates within runs
- add rates to the DQM Playground website (write model, management script, basic data visualization, API, ...)
- build model to predict rate of a given lumisection based on previous rates
- build model to predict bad lumisections based on a combination of significant trigger paths (a drop in the rate doesn't necessarily mean that a lumisection is bad, but a loss in correlation between rates might)

## Resources

__OMS__

- [OMS API instructions](https://indico.cern.ch/event/997758/contributions/4191705/attachments/2173881/3670409/OMS%20CERN%20OpenID%20migration%20-%20update.pdf)
- [OMS API client](https://gitlab.cern.ch/cmsoms/oms-api-client)
- [OMS API endpoints](https://cmsoms.cern.ch/agg/api/v1/version/endpoints)

- [OMS run page](https://cmsoms.cern.ch/cms/runs/report?cms_run=315689&cms_run_sequence=GLOBAL-RUN)
- [OMS L1 rate page](https://cmsoms.cern.ch/cms/triggers/l1_rates?cms_run=315689&props.11273_11270.selectedCells=L1A%20physics:2)
- [OMS HLT rate page](https://cmsoms.cern.ch/cms/triggers/hlt_trigger_rates?cms_run=315689&props.11280_11278.selectedCells=Physics:2)

__Time serie analysis__

- [Time Series with Python](https://app.datacamp.com/learn/skill-tracks/time-series-with-python)
- [Time Series / Sequential Data study group](https://forums.fast.ai/t/time-series-sequential-data-study-group/29686)
- [Gramian Angular Field](https://medium.com/analytics-vidhya/encoding-time-series-as-images-b043becbdbf3)

__Recurrent Neural Networks__

- [Understanding LSTM Networks](https://colah.github.io/posts/2015-08-Understanding-LSTMs/)
- [The Unreasonable Effectiveness of RNN](https://karpathy.github.io/2015/05/21/rnn-effectiveness/)
- [Classifying Names with a Character-Level RNN](https://pytorch.org/tutorials/intermediate/char_rnn_classification_tutorial.html)
- [Generating Names with a Character-Level RNN](https://pytorch.org/tutorials/intermediate/char_rnn_generation_tutorial.html)

__Finance__

- [Finance Fundamentals with Python](https://app.datacamp.com/learn/skill-tracks/finance-fundamentals-in-python)
