# Introduction

Notes are the actions or events generated by accounts, such as writing a blog post, getting a NFT dynamic, donation to others, etc.

## API

```ts
const notes: Note = unidata.notes.get(options: {
    source: string;
    identity: string;
    last?: string;
    limit?: number;
});
```

## Specification

All returned data conform to the following specification.

```ts
type Notes = {
    date_created: string;
    date_updated: string;

    related_urls?: string[];

    tags?: string[];
    authors: AccountInstanceURI[];
    title?: string;
    summary?: string;
    attachments?: {
        type?: string;
        content?: string;
        address?: URI;
        mime_type: string;
        size_in_bytes?: number;
    }[];

    source: AssetSource | NoteSource;

    metadata?: {
        network: Network;
        proof: string;

        [key: string]: any;
    };
}[];
```