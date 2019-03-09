# SSB Roadmap

> A roadmap diagram detailing the what needs to be done next, to advance some SSB projects

**Feel free to edit the graph below with [Mermaid syntax](https://mermaidjs.github.io/).**

```mermaid
graph LR
    %%%%%%%%%%%%%%%%%%%%%%
    %% TASK DEFINITIONS %%
    %%%%%%%%%%%%%%%%%%%%%%

    protocol-docs %% https://ssbc.github.io/scuttlebutt-protocol-guide/
    docs-website-aggregation %% website renewal and centralization
    gossip-refactor %% @staltz is doing this
    ssb-conn-db %% @staltz is doing this
    ssb-conn-hub %% @staltz is doing this
    ssb-conn-utils %% @staltz is doing this
    ssb-legacy-conn %% @staltz is doing this
    ssb-friends3
    same-as
    muxrpc-push-stream %% maybe @dominic is doing this
    soft-edit-msg
    wiki-msg
    account-milestones
    offlog-online-authenticated-chat

    subgraph performance
        rust-ssb %% sunrise choir is doing this
        ssb-binary-database %% maybe @dominic is doing this
        pull-drain-gently %% idea from @staltz
        gently-build-flume-indexes
        lazy-indexes
        holding-tank-log
        replicate-close-friends-first
        gentle-flume-index-building
    end

    subgraph servers
        ssb-tunnel %% done by dominic, needs testing in the real world
        cjdns-nodejs-bindings
        multiserver-cjdns
        rooms %% idea from @staltz
        ssb-dht-invites %% https://gitlab.com/staltz/ssb-dht-invite
        broadcast-pubs %% idea from @staltz
        hyperswarm-usage
        dht-invites-in-production
        ssb-bluetooth %% https://github.com/Happy0/ssb-bluetooth/
    end

    subgraph free listening
       private-block
       private-block-in-production
       auditable-user-invites
       ssb-lists
       ssb-lists-in-production
    end

    subgraph trust and safety
        blame-a-blob
        byte-count-per-feed
        storage-usage-stats
        hop-2-usernames
        publicWebHosting
        publicWebHosting-config-in-apps
        flag-a-msg
        delete-blob
        block-blob
        blob-management
        delete-blobs-of-user
        delete-feed-from-flume
        soft-delete-msg
        private-groups
    end

    %%%%%%%%%%%%%%%%%%%%%%%%
    %% STATUS DEFINITIONS %%
    %%%%%%%%%%%%%%%%%%%%%%%%
    %% To do:
    class rooms,gossip-refactor,ssb-lists-in-production,flag-a-msg,blame-a-blob,byte-count-per-feed,storage-usage-stats,hop-2-usernames,publicWebHosting-config-in-apps,blob-management,block-blob,delete-feed-from-flume,delete-blobs-of-user,soft-edit-msg,soft-delete-msg,wiki-msg,pull-drain-gently,gently-build-flume-indexes,lazy-indexes,replicate-close-friends-first,account-milestones,offlog-online-authenticated-chat,docs-website-aggregation,cjdns-nodejs-bindings,multiserver-cjdns,holding-tank-log,gentle-flume-index-building,ssb-conn-utils,broadcast-pubs todo

    %% Work in progress:
    class ssb-tunnel,rust-ssb,same-as,muxrpc-push-stream,private-groups,private-block-in-production,auditable-user-invites,ssb-binary-database,hyperswarm-usage,dht-invites-in-production,ssb-conn-hub,ssb-legacy-conn wip

    %% Done:
    class protocol-docs,ssb-friends3,private-block,ssb-lists,publicWebHosting,delete-blob,ssb-dht-invites,ssb-conn-db,ssb-bluetooth done

    %%%%%%%%%%%%%%%%%%%%%%%
    %% ORDER CONSTRAINTS %%
    %%%%%%%%%%%%%%%%%%%%%%%

    protocol-docs --> rust-ssb
    protocol-docs --> docs-website-aggregation
    ssb-tunnel --> rooms
    ssb-friends3 --> same-as
    same-as --> account-milestones
    ssb-lists --> ssb-lists-in-production
    private-block --> private-block-in-production
    blame-a-blob --> byte-count-per-feed
    byte-count-per-feed --> storage-usage-stats
    publicWebHosting --> publicWebHosting-config-in-apps
    delete-blob --> blob-management
    block-blob --> blob-management
    blame-a-blob --> delete-blobs-of-user
    delete-blobs-of-user --> delete-feed-from-flume
    soft-edit-msg --> soft-delete-msg
    soft-edit-msg --> wiki-msg
    pull-drain-gently --> gently-build-flume-indexes
    gently-build-flume-indexes --> replicate-close-friends-first
    rooms --> offlog-online-authenticated-chat
    cjdns-nodejs-bindings --> multiserver-cjdns
    ssb-dht-invites --> dht-invites-in-production
    hyperswarm-usage --> dht-invites-in-production
    holding-tank-log --> gentle-flume-index-building
    pull-drain-gently --> gentle-flume-index-building
    ssb-conn-db --> ssb-legacy-conn
    ssb-conn-hub --> ssb-legacy-conn
    ssb-conn-utils --> ssb-legacy-conn
    ssb-legacy-conn --> gossip-refactor
    gossip-refactor --> rooms
    gossip-refactor --> broadcast-pubs

    %%%%%%%%%%%%
    %% Styles %%
    %%%%%%%%%%%%
    classDef cluster opacity:0.25;
    classDef todo fill:#fbb,stroke-width:0px;
    classDef wip fill:#ee7,stroke-width:0px;
    classDef done fill:#7e7,stroke-width:0px;
```

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons Licence" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
