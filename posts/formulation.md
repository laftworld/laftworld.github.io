
**[Generative Adversarial Nets]** Goodfellow, Ian, et al. "Generative adversarial nets." Advances in neural information processing systems. 2014. [[Link]](http://papers.nips.cc/paper/5423-generative-adversarial-nets.pdf)
\[
\lim_{\sigma\to 0} \nabla_{\pmb{x}}\mathbb{E}_{\epsilon \sim \mathcal{N}(0,\sigma^2 \pmb{I})} f(\pmb{x}+\epsilon) = \nabla_{\pmb{x}}f(\pmb{x})
\]

\[
\min_G\max_D V(D,G) = \mathbb{E}_{\pmb{x}\sim p_{\text{data}}(\pmb{x})}[\log D(\pmb{x})]+\mathbb{E}_{\pmb{z}\sim p_{\pmb{z}}(\pmb{z})}[\log(1-D(G(\pmb{z})))].
\]
