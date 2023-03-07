<script>
    import Toggler from "@/components/Toggler.svelte";

    export let compact = false;
</script>

<header class="page-header">
    <div class="wrapper wrapper-lg">
        <a href="/" class="logo" class:logo-sm={compact}>
            <img src="/images/logo.svg" alt="Agência Proideas logo" width="40" height="40" />
            <span class="txt">Agência <strong>Proideas</strong></span>
            <span class="version">{import.meta.env.PB_VERSION}</span>
        </a>

        <div class="flex-fill" />

        <slot />

        <button type="button" class="btn btn-circle btn-secondary responsive-menu-btn" title="Menu">
            <span />
            <i class="ri-menu-3-fill" />
            <Toggler class="dropdown dropdown-lg dropdown-right dropdown-nowrap responsive-menu-dropdown">
                <a href="#" class="dropdown-item">Sobre</a>
                <a
                    href={import.meta.env.PB_DISCUSSIONS_URL}
                    class="dropdown-item"
                    target="_blank"
                    rel="noreferrer noopener"
                >
                    Serviços
                </a>
                <a href="#" class="dropdown-item">Suporte</a>
                <hr />
                <a href="#" class="dropdown-item">
                    <span class="txt">Agendar reunião</span>
                </a>
            </Toggler>
        </button>

        <nav class="main-menu">
            <a href="#" class="btn btn-secondary">Sobre</a>
            <a
                href={import.meta.env.PB_DISCUSSIONS_URL}
                class="btn btn-secondary"
                target="_blank"
                rel="noreferrer noopener"
            >
                Serviços
            </a>
            <a href="#" class="btn btn-secondary">Suporte</a>
            <a
                href={import.meta.env.PB_REPO_URL}
                class="btn btn-circle btn-secondary"
                target="_blank"
                rel="noreferrer noopener"
                title="GitHub Repo"
            >
                <i class="ri-github-line" />
            </a>
            <a href="#" class="btn btn-outline btn-expanded">
                <span class="txt">Agendar Reunião</span>
            </a>
        </nav>
    </div>
</header>
