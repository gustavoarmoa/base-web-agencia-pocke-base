<script>
    import Toc from "@/components/Toc.svelte";
    import AppHooks from "./AppHooks.svelte";
    import ModelHooks from "./ModelHooks.svelte";
    import MailerHooks from "./MailerHooks.svelte";
    import RecordCrudHooks from "./RecordCrudHooks.svelte";
    import RecordAuthHooks from "./RecordAuthHooks.svelte";
    import RealtimeHooks from "./RealtimeHooks.svelte";
    import FileHooks from "./FileHooks.svelte";
    import AdminCrudHooks from "./AdminCrudHooks.svelte";
    import AdminAuthHooks from "./AdminAuthHooks.svelte";
    import CollectionHooks from "./CollectionHooks.svelte";
    import SettingsHooks from "./SettingsHooks.svelte";
</script>

<p>
    The standard way to modify the default PocketBase behavior is through
    <strong>event hooks</strong> in your Go code.
    <br />
    Each event hook has 3 public methods:
</p>
<ul>
    <li class="m-b-10">
        <code class="txt-bold">PreAdd(fn)</code>
        - prepend a new listener callback function to the specified event hook.
        <br />
        Returning an error or <code>hook.StopPropagation</code> in the callback function stops the listeners execution
        chain.
    </li>
    <li class="m-b-10">
        <code class="txt-bold">Add(fn)</code>
        - append a new listener callback function to the specified event hook.
        <br />
        Returning an error or <code>hook.StopPropagation</code> in the callback function stops the listeners execution
        chain.
    </li>
    <li class="m-b-10">
        <code class="txt-bold">Trigger(data)</code>
        - triggers the event hook, aka. executes its listeners in the order they were added.
        <br />
        <em class="txt-hint">This method usually is not called manually by users.</em>
    </li>
</ul>

<p>
    Some event hooks, like the DB and Record API hooks, are "proxy" hooks and support an optional tags filter
    list. If the tags list (eg. collection ids/names) is specified, then all event handlers registered via the
    proxy hook will be triggered and called only if their event data origin matches the tag(s).
</p>

<p>You can explore all available event hooks below:</p>
<Toc />

<AppHooks />
<ModelHooks />
<MailerHooks />
<RecordCrudHooks />
<RecordAuthHooks />
<RealtimeHooks />
<FileHooks />
<CollectionHooks />
<SettingsHooks />
<AdminCrudHooks />
<AdminAuthHooks />
