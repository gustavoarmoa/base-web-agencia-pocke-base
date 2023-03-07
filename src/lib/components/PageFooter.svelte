<script>
    import { onMount } from "svelte";
    import tooltip from "@/actions/tooltip";

    // build seperately for very basic spam protection
    let supportEmail = "support";
    onMount(() => {
        setTimeout(() => {
            supportEmail += "@" + "pocketbase.io";
        }, 1000);
    });
</script>

<footer class="page-footer">
    <div class="wrapper wrapper-lg">
        <div class="primary-bar">
            <nav class="footer-col links">
                <a href="#" class="link-item">Sobre</a>
                <a href={import.meta.env.PB_DISCUSSIONS_URL} class="link-item" target="_blank" rel="noopener noreferrer">
                    Serviços
                </a>
                <a href="#" class="link-item">Suporte</a>
            </nav>

            <nav class="footer-col links">
                <a href="#" class="link-item">Materiais</a>
                <a href={import.meta.env.PB_JS_SDK_URL} class="link-item" target="_blank" rel="noopener noreferrer">
                    JavaScript SDK
                </a>
                <a href={import.meta.env.PB_DART_SDK_URL} class="link-item" target="_blank" rel="noopener noreferrer">
                    Dart SDK
                </a>
            </nav>

            <div class="footer-col socials">
                <div class="watermark-logo">Agência <strong>Proideas</strong></div>
                <a
                    href="mailto:{supportEmail}"
                    class="btn btn-secondary btn-circle btn-hint social-item"
                    aria-label="Contact support"
                    use:tooltip={{ text: "Contact " + supportEmail, position: "top" }}
                >
                    <i class="ri-mail-line" />
                </a>
                <a
                    href={import.meta.env.PB_TWITTER_URL}
                    rel="noopener noreferrer"
                    target="_blank"
                    class="btn btn-secondary btn-circle btn-hint social-item"
                    aria-label="Go to Twitter"
                    use:tooltip={{ text: "Go to Twitter", position: "top" }}
                >
                    <i class="ri-twitter-line" />
                </a>
                <a
                    href={import.meta.env.PB_REPO_URL}
                    rel="noopener noreferrer"
                    target="_blank"
                    class="btn btn-secondary btn-circle btn-hint social-item"
                    aria-label="Go to GitHub"
                    use:tooltip={{ text: "Go to GitHub", position: "top" }}
                >
                    <i class="ri-github-line" />
                </a>
            </div>
        </div>
        <div class="secondary-bar">
            <div class="terms">
                <span class="txt">
                    © {new Date().getFullYear()} Agência <strong>Proideas</strong>
                </span>
                <span class="gopher-credit">
                    Todos os direitos reservados
                    <a
                        href="#"
                        target="_blank"
                        rel="noreferrer noopener"
                    >
                        Termos de uso
                    </a>
                </span>
            </div>
            <div class="flex-fill" />
            <div class="credit">
                Crafted by <a href="#" target="_blank" rel="noopener noreferrer" class="link-hint">
                    <strong>Boxsales</strong>
                </a>
            </div>
        </div>
    </div>
</footer>
