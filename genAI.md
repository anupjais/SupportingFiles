## the output on
```
const API_KEY = process.env.OPENAI_API_KEY;

const openai = (await import("openai")).default;
const client = new openai.OpenAI({
    apiKey: API_KEY,
});
```

```

◇ injected env (1) from .env // tip: ◈ encrypted .env [www.dotenvx.com]
OpenAI client initialize successfully
<ref *1> OpenAI {
  completions: Completions { _client: [Circular *1] },
  chat: Chat {
    _client: [Circular *1],
    completions: Completions { _client: [Circular *1], messages: [Messages] }
  },
  embeddings: Embeddings { _client: [Circular *1] },
  files: Files { _client: [Circular *1] },
  images: Images { _client: [Circular *1] },
  contentProvenanceChecks: ContentProvenanceChecks { _client: [Circular *1] },
  audio: Audio {
    _client: [Circular *1],
    transcriptions: Transcriptions { _client: [Circular *1] },
    translations: Translations { _client: [Circular *1] },
    speech: Speech { _client: [Circular *1] }
  },
  moderations: Moderations { _client: [Circular *1] },
  models: Models { _client: [Circular *1] },
  fineTuning: FineTuning {
    _client: [Circular *1],
    methods: Methods { _client: [Circular *1] },
    jobs: Jobs { _client: [Circular *1], checkpoints: [Checkpoints] },
    checkpoints: Checkpoints { _client: [Circular *1], permissions: [Permissions] },
    alpha: Alpha { _client: [Circular *1], graders: [Graders] }
  },
  graders: Graders {
    _client: [Circular *1],
    graderModels: GraderModels { _client: [Circular *1] }
  },
  vectorStores: VectorStores {
    _client: [Circular *1],
    files: Files { _client: [Circular *1] },
    fileBatches: FileBatches { _client: [Circular *1] }
  },
  safety: Safety {
    _client: [Circular *1],
    alerts: Alerts { _client: [Circular *1] }
  },
  webhooks: Webhooks { _client: [Circular *1] },
  beta: Beta {
    _client: [Circular *1],
    realtime: Realtime {
      _client: [Circular *1],
      sessions: [Sessions],
      transcriptionSessions: [TranscriptionSessions]
    },
    responses: Responses {
      _client: [Circular *1],
      inputItems: [InputItems],
      inputTokens: [InputTokens]
    },
    chatkit: ChatKit {
      _client: [Circular *1],
      sessions: [Sessions],
      threads: [Threads]
    },
    assistants: Assistants { _client: [Circular *1] },
    threads: Threads {
      _client: [Circular *1],
      runs: [Runs],
      messages: [Messages]
    }
  },
  batches: Batches { _client: [Circular *1] },
  uploads: Uploads {
    _client: [Circular *1],
    parts: Parts { _client: [Circular *1] }
  },
  admin: Admin {
    _client: [Circular *1],
    organization: Organization {
      _client: [Circular *1],
      auditLogs: [AuditLogs],
      adminAPIKeys: [AdminAPIKeys],
      usage: [Usage],
      invites: [Invites],
      users: [Users],
      groups: [Groups],
      roles: [Roles],
      dataRetention: [DataRetention],
      spendLimit: [SpendLimit],
      spendAlerts: [SpendAlerts],
      certificates: [Certificates],
      projects: [Projects]
    }
  },
  responses: Responses {
    _client: [Circular *1],
    inputItems: InputItems { _client: [Circular *1] },
    inputTokens: InputTokens { _client: [Circular *1] }
  },
  realtime: Realtime {
    _client: [Circular *1],
    clientSecrets: ClientSecrets { _client: [Circular *1] },
    calls: Calls { _client: [Circular *1] }
  },
  conversations: Conversations {
    _client: [Circular *1],
    items: Items { _client: [Circular *1] }
  },
  evals: Evals {
    _client: [Circular *1],
    runs: Runs { _client: [Circular *1], outputItems: [OutputItems] }
  },
  containers: Containers {
    _client: [Circular *1],
    files: Files { _client: [Circular *1], content: [Content] }
  },
  skills: Skills {
    _client: [Circular *1],
    content: Content { _client: [Circular *1] },
    versions: Versions { _client: [Circular *1], content: [Content] }
  },
  videos: Videos { _client: [Circular *1] },
  baseURL: 'https://api.openai.com/v1',
  timeout: 600000,
  logger: Object [console] {
    log: [Function: log],
    info: [Function: info],
    debug: [Function: debug],
    warn: [Function: warn],
    error: [Function: error],
    dir: [Function: dir],
    time: [Function: time],
    timeEnd: [Function: timeEnd],
    timeLog: [Function: timeLog],
    trace: [Function: trace],
    assert: [Function: assert],
    clear: [Function: clear],
    count: [Function: count],
    countReset: [Function: countReset],
    group: [Function: group],
    groupEnd: [Function: groupEnd],
    table: [Function: table],
    dirxml: [Function: dirxml],
    groupCollapsed: [Function: groupCollapsed],
    Console: [Function: Console],
    profile: [Function: profile],
    profileEnd: [Function: profileEnd],
    timeStamp: [Function: timeStamp],
    context: [Function: context],
    createTask: [Function: createTask]
  },
  logLevel: 'warn',
  fetchOptions: undefined,
  maxRetries: 2,
  fetch: [Function: fetch],
  _options: {
    apiKey: '',
    adminAPIKey: null,
    organization: null,
    project: null,
    webhookSecret: null,
    workloadIdentity: undefined,
    x509Transport: undefined,
    provider: undefined,
    baseURL: 'https://api.openai.com/v1'
  },
  _provider: undefined,
  apiKey: '',
  adminAPIKey: null,
  organization: null,
  project: null,
  webhookSecret: null
}
```
