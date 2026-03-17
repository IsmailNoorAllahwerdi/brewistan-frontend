<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Brewistan — Digital Loyalty for Cafés</title>
<meta name="description" content="Replace paper punch cards with a beautiful digital stamp system. Brewistan helps independent cafés and chains build loyalty, drive repeat visits, and grow revenue.">
<meta name="theme-color" content="#1A1209">
<link rel="canonical" href="https://www.brewistan.com">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
:root{--espresso:#1A1209;--crema:#F5EDE3;--latte:#FAF7F2;--caramel:#C8853B;--caramel-light:#E8A84C;--mocha:#6B4226;--steam:#FFFFFF;--charcoal:#2D2A26;--warm-gray:#8A8279;--light-line:rgba(26,18,9,0.08);--danger:#D32F2F;--success:#2E7D32;--success-bg:#E8F5E9;--info:#1565C0;--info-bg:#E3F2FD;--font-display:'DM Serif Display',Georgia,serif;--font-body:'Plus Jakarta Sans',system-ui,sans-serif;--space-xs:8px;--space-sm:16px;--space-md:24px;--space-lg:40px;--space-xl:64px;--space-2xl:96px;--space-3xl:128px;--max-w:1200px;--radius:16px;--radius-sm:10px}
html{scroll-behavior:smooth;-webkit-font-smoothing:antialiased}
body{font-family:var(--font-body);color:var(--espresso);background:var(--latte);line-height:1.65;overflow-x:hidden}
a{color:inherit;text-decoration:none}img{max-width:100%;display:block}button{font-family:inherit;cursor:pointer;border:none}
.container{max-width:var(--max-w);margin:0 auto;padding:0 var(--space-md)}
body::before{content:'';position:fixed;inset:0;z-index:9999;pointer-events:none;opacity:0.025;background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");background-size:200px}

/* Pages & Transitions */
.page{display:none;opacity:0;transition:opacity 0.35s ease}.page.active{display:block}.page.visible{opacity:1}
.reveal{opacity:0;transform:translateY(32px);transition:opacity 0.7s cubic-bezier(0.16,1,0.3,1),transform 0.7s cubic-bezier(0.16,1,0.3,1)}.reveal.visible{opacity:1;transform:translateY(0)}.reveal-delay-1{transition-delay:.1s}.reveal-delay-2{transition-delay:.2s}.reveal-delay-3{transition-delay:.3s}.reveal-delay-4{transition-delay:.4s}

/* Nav */
.nav{position:fixed;top:0;left:0;right:0;z-index:1000;padding:var(--space-sm) 0;transition:background .4s,backdrop-filter .4s,box-shadow .4s}.nav.scrolled{background:rgba(250,247,242,0.85);backdrop-filter:blur(20px);-webkit-backdrop-filter:blur(20px);box-shadow:0 1px 0 var(--light-line)}.nav.nav-solid{background:rgba(250,247,242,0.95);backdrop-filter:blur(20px);box-shadow:0 1px 0 var(--light-line)}
.nav-inner{max-width:var(--max-w);margin:0 auto;padding:0 var(--space-md);display:flex;align-items:center;justify-content:space-between;height:56px}
.nav-logo{font-family:var(--font-display);font-size:24px;color:var(--espresso);letter-spacing:-0.02em;cursor:pointer}.nav-logo span{color:var(--caramel)}
.nav-links{display:flex;align-items:center;gap:var(--space-md)}.nav-links a{font-size:14px;font-weight:500;color:var(--warm-gray);transition:color .25s;cursor:pointer}.nav-links a:hover{color:var(--espresso)}
.nav-cta{background:var(--espresso);color:var(--crema)!important;padding:10px 22px;border-radius:100px;font-size:14px;font-weight:600;transition:background .25s,transform .25s}.nav-cta:hover{background:var(--mocha);transform:translateY(-1px)}
.nav-mobile-toggle{display:none;background:none;width:32px;height:32px;flex-direction:column;align-items:center;justify-content:center;gap:6px}.nav-mobile-toggle span{display:block;width:22px;height:2px;background:var(--espresso);border-radius:2px}
.nav-user-menu{display:flex;align-items:center;gap:var(--space-sm)}
.nav-avatar{width:36px;height:36px;border-radius:50%;background:var(--caramel);color:var(--steam);display:flex;align-items:center;justify-content:center;font-weight:700;font-size:14px;cursor:pointer;transition:transform .2s}.nav-avatar:hover{transform:scale(1.08)}
.nav-user-name{font-size:14px;font-weight:600}
.nav-logout{font-size:13px;color:var(--warm-gray);cursor:pointer;padding:6px 14px;border-radius:100px;border:1px solid var(--light-line);transition:all .2s;background:none}.nav-logout:hover{border-color:var(--danger);color:var(--danger)}

/* Hero */
.hero{min-height:100vh;display:flex;align-items:center;position:relative;overflow:hidden;padding:var(--space-3xl) 0 var(--space-2xl)}.hero::before{content:'';position:absolute;top:-20%;right:-10%;width:600px;height:600px;background:radial-gradient(circle,rgba(200,133,59,0.12) 0%,transparent 70%);border-radius:50%;pointer-events:none}.hero::after{content:'';position:absolute;bottom:-10%;left:-5%;width:400px;height:400px;background:radial-gradient(circle,rgba(200,133,59,0.08) 0%,transparent 70%);border-radius:50%;pointer-events:none}
.hero-inner{max-width:var(--max-w);margin:0 auto;padding:0 var(--space-md);display:grid;grid-template-columns:1fr 1fr;gap:var(--space-xl);align-items:center}
.hero-badge{display:inline-flex;align-items:center;gap:var(--space-xs);background:rgba(200,133,59,0.1);border:1px solid rgba(200,133,59,0.2);padding:6px 16px;border-radius:100px;font-size:13px;font-weight:600;color:var(--mocha);margin-bottom:var(--space-md)}.hero-badge::before{content:'';width:6px;height:6px;background:var(--caramel);border-radius:50%;animation:pulse-dot 2s ease-in-out infinite}
@keyframes pulse-dot{0%,100%{opacity:1;transform:scale(1)}50%{opacity:.5;transform:scale(1.5)}}
.hero h1{font-family:var(--font-display);font-size:clamp(42px,5.5vw,72px);line-height:1.08;letter-spacing:-0.03em;margin-bottom:var(--space-md)}.hero h1 em{font-style:italic;color:var(--caramel)}
.hero-sub{font-size:18px;color:var(--warm-gray);max-width:460px;line-height:1.7;margin-bottom:var(--space-lg)}
.hero-buttons{display:flex;gap:var(--space-sm);flex-wrap:wrap}

/* Buttons */
.btn-primary{background:var(--espresso);color:var(--crema);padding:16px 36px;border-radius:100px;font-size:16px;font-weight:600;transition:all .3s cubic-bezier(0.16,1,0.3,1);display:inline-flex;align-items:center;gap:var(--space-xs);cursor:pointer;border:none}.btn-primary:hover{background:var(--mocha);transform:translateY(-2px);box-shadow:0 8px 32px rgba(26,18,9,0.2)}
.btn-secondary{background:transparent;color:var(--espresso);padding:16px 36px;border-radius:100px;font-size:16px;font-weight:600;border:1.5px solid var(--light-line);transition:all .3s;cursor:pointer}.btn-secondary:hover{border-color:var(--espresso);background:rgba(26,18,9,0.03)}
.btn-sm{padding:10px 24px;font-size:14px}.btn-caramel{background:var(--caramel);color:var(--steam)}.btn-caramel:hover{background:var(--caramel-light)}.btn-block{width:100%;justify-content:center;text-align:center}
.btn-cta-light{background:var(--crema);color:var(--espresso);padding:16px 40px;border-radius:100px;font-size:16px;font-weight:600;display:inline-flex;align-items:center;gap:var(--space-xs);transition:all .3s cubic-bezier(0.16,1,0.3,1);cursor:pointer;border:none}.btn-cta-light:hover{transform:translateY(-2px);box-shadow:0 8px 32px rgba(0,0,0,0.3)}

/* Phone Mockup */
.hero-visual{display:flex;justify-content:center;align-items:center;position:relative}
.phone-mockup{width:280px;height:560px;background:var(--espresso);border-radius:40px;padding:12px;position:relative;box-shadow:0 40px 80px rgba(26,18,9,0.25),0 0 0 1px rgba(255,255,255,0.1) inset;transform:rotate(2deg);transition:transform .5s cubic-bezier(0.16,1,0.3,1)}.phone-mockup:hover{transform:rotate(0deg) scale(1.02)}
.phone-screen{width:100%;height:100%;background:var(--latte);border-radius:30px;overflow:hidden;position:relative}
.phone-notch{width:120px;height:28px;background:var(--espresso);border-radius:0 0 18px 18px;margin:0 auto;position:relative;z-index:2}
.phone-content{padding:16px}.phone-greeting{font-size:11px;color:var(--warm-gray);margin-bottom:2px}.phone-user{font-family:var(--font-display);font-size:20px;margin-bottom:16px}
.phone-card{background:linear-gradient(135deg,var(--mocha),var(--caramel));border-radius:16px;padding:16px;color:var(--steam);margin-bottom:12px}.phone-card-name{font-size:13px;font-weight:600;margin-bottom:10px;opacity:.9}
.phone-stamps{display:grid;grid-template-columns:repeat(5,1fr);gap:8px}.phone-stamp{width:100%;aspect-ratio:1;border-radius:50%;background:rgba(255,255,255,0.2);display:flex;align-items:center;justify-content:center;font-size:14px}.phone-stamp.filled{background:rgba(255,255,255,0.95)}
.phone-progress-text{font-size:11px;margin-top:10px;opacity:.8}
.phone-reward-card{background:var(--steam);border:1.5px solid var(--light-line);border-radius:12px;padding:12px;display:flex;align-items:center;gap:10px}.phone-reward-icon{width:40px;height:40px;background:rgba(200,133,59,0.12);border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:18px;flex-shrink:0}.phone-reward-info{flex:1}.phone-reward-title{font-size:12px;font-weight:600}.phone-reward-desc{font-size:10px;color:var(--warm-gray)}
.float-badge{position:absolute;background:var(--steam);border-radius:12px;padding:10px 16px;box-shadow:0 8px 32px rgba(26,18,9,0.1);display:flex;align-items:center;gap:8px;font-size:13px;font-weight:600;white-space:nowrap;animation:float 4s ease-in-out infinite}.float-badge-1{top:15%;left:-20px}.float-badge-2{bottom:20%;right:-30px;animation-delay:1.5s}
@keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-8px)}}
.float-icon{width:28px;height:28px;border-radius:8px;display:flex;align-items:center;justify-content:center;font-size:14px}.float-icon.green{background:#E8F5E9}.float-icon.amber{background:#FFF3E0}

/* Section Headers */
.section-label{display:inline-flex;align-items:center;gap:8px;font-size:13px;font-weight:700;letter-spacing:0.08em;text-transform:uppercase;color:var(--caramel);margin-bottom:var(--space-sm)}.section-label::before{content:'';width:20px;height:2px;background:var(--caramel);border-radius:2px}
.section-title{font-family:var(--font-display);font-size:clamp(32px,4vw,48px);line-height:1.15;letter-spacing:-0.02em;margin-bottom:var(--space-sm)}.section-sub{font-size:17px;color:var(--warm-gray);max-width:540px;line-height:1.7}

/* Features */
.features{padding:var(--space-3xl) 0}.features-header{text-align:center;margin-bottom:var(--space-xl);display:flex;flex-direction:column;align-items:center}
.features-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:var(--space-md)}
.feature-card{background:var(--steam);border:1px solid var(--light-line);border-radius:var(--radius);padding:var(--space-lg) var(--space-md);transition:all .4s cubic-bezier(0.16,1,0.3,1);position:relative;overflow:hidden}.feature-card::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--caramel),var(--caramel-light));opacity:0;transition:opacity .4s}.feature-card:hover{transform:translateY(-4px);box-shadow:0 16px 48px rgba(26,18,9,0.08);border-color:transparent}.feature-card:hover::before{opacity:1}
.feature-icon{width:52px;height:52px;border-radius:14px;display:flex;align-items:center;justify-content:center;font-size:24px;margin-bottom:var(--space-md)}.feature-icon.warm{background:rgba(200,133,59,0.1)}.feature-icon.green{background:rgba(76,175,80,0.1)}.feature-icon.blue{background:rgba(66,133,244,0.1)}.feature-icon.purple{background:rgba(156,39,176,0.1)}.feature-icon.red{background:rgba(229,57,53,0.1)}.feature-icon.teal{background:rgba(0,150,136,0.1)}
.feature-card h3{font-family:var(--font-display);font-size:22px;margin-bottom:var(--space-xs)}.feature-card p{font-size:15px;color:var(--warm-gray);line-height:1.65}

/* How It Works */
.how-it-works{padding:var(--space-3xl) 0;background:var(--espresso);color:var(--crema);position:relative;overflow:hidden}.how-it-works::before{content:'';position:absolute;top:0;right:0;width:500px;height:500px;background:radial-gradient(circle,rgba(200,133,59,0.15) 0%,transparent 70%);pointer-events:none}
.how-header{text-align:center;margin-bottom:var(--space-xl);display:flex;flex-direction:column;align-items:center}.how-header .section-sub{color:rgba(245,237,227,0.6)}
.how-tracks{display:grid;grid-template-columns:1fr 1fr;gap:var(--space-lg)}.how-track{background:rgba(255,255,255,0.04);border:1px solid rgba(255,255,255,0.08);border-radius:var(--radius);padding:var(--space-lg)}
.how-track-label{display:inline-block;font-size:11px;font-weight:700;letter-spacing:0.1em;text-transform:uppercase;padding:4px 12px;border-radius:100px;margin-bottom:var(--space-md)}.how-track-label.owner{background:rgba(200,133,59,0.2);color:var(--caramel-light)}.how-track-label.customer{background:rgba(76,175,80,0.15);color:#81C784}
.how-steps{display:flex;flex-direction:column;gap:var(--space-md)}.how-step{display:flex;align-items:flex-start;gap:var(--space-sm)}.how-step-num{width:32px;height:32px;border-radius:50%;background:rgba(255,255,255,0.08);border:1px solid rgba(255,255,255,0.15);display:flex;align-items:center;justify-content:center;font-size:13px;font-weight:700;flex-shrink:0;margin-top:2px}.how-step-text h4{font-family:var(--font-display);font-size:18px;margin-bottom:4px}.how-step-text p{font-size:14px;color:rgba(245,237,227,0.55);line-height:1.6}

/* Pricing */
.pricing{padding:var(--space-3xl) 0}.pricing-header{text-align:center;margin-bottom:var(--space-xl);display:flex;flex-direction:column;align-items:center}
.pricing-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:var(--space-md)}
.pricing-card{background:var(--steam);border:1.5px solid var(--light-line);border-radius:var(--radius);padding:var(--space-lg);position:relative;transition:all .4s cubic-bezier(0.16,1,0.3,1)}.pricing-card:hover{transform:translateY(-4px);box-shadow:0 16px 48px rgba(26,18,9,0.08)}.pricing-card.featured{border-color:var(--caramel);box-shadow:0 16px 48px rgba(200,133,59,0.12)}.pricing-card.featured::before{content:'Most Popular';position:absolute;top:-13px;left:50%;transform:translateX(-50%);background:linear-gradient(135deg,var(--caramel),var(--caramel-light));color:var(--steam);font-size:12px;font-weight:700;padding:4px 16px;border-radius:100px}
.pricing-tier{font-size:13px;font-weight:700;text-transform:uppercase;letter-spacing:0.08em;color:var(--caramel);margin-bottom:var(--space-xs)}.pricing-price{font-family:var(--font-display);font-size:44px;letter-spacing:-0.03em;margin-bottom:4px}.pricing-price span{font-family:var(--font-body);font-size:15px;color:var(--warm-gray);font-weight:400}.pricing-desc{font-size:14px;color:var(--warm-gray);margin-bottom:var(--space-md);padding-bottom:var(--space-md);border-bottom:1px solid var(--light-line)}
.pricing-features{list-style:none;display:flex;flex-direction:column;gap:12px;margin-bottom:var(--space-lg)}.pricing-features li{font-size:14px;display:flex;align-items:center;gap:10px;color:var(--charcoal)}.pricing-features li::before{content:'✓';color:var(--caramel);font-weight:700;font-size:13px;flex-shrink:0}
.pricing-btn{display:block;width:100%;text-align:center;padding:14px;border-radius:100px;font-size:15px;font-weight:600;transition:all .3s;cursor:pointer}.pricing-btn.primary{background:var(--espresso);color:var(--crema);border:none}.pricing-btn.primary:hover{background:var(--mocha)}.pricing-btn.outline{background:transparent;color:var(--espresso);border:1.5px solid var(--light-line)}.pricing-btn.outline:hover{border-color:var(--espresso)}

/* CTA */
.cta{padding:var(--space-3xl) 0}.cta-box{background:var(--espresso);border-radius:24px;padding:var(--space-2xl) var(--space-xl);text-align:center;position:relative;overflow:hidden}.cta-box::before{content:'';position:absolute;top:-50%;left:-20%;width:500px;height:500px;background:radial-gradient(circle,rgba(200,133,59,0.2) 0%,transparent 60%);pointer-events:none}.cta-box::after{content:'';position:absolute;bottom:-40%;right:-15%;width:400px;height:400px;background:radial-gradient(circle,rgba(200,133,59,0.1) 0%,transparent 60%);pointer-events:none}
.cta-content{position:relative;z-index:1}.cta-content h2{font-family:var(--font-display);font-size:clamp(32px,4vw,48px);color:var(--crema);margin-bottom:var(--space-sm);letter-spacing:-0.02em}.cta-content h2 em{color:var(--caramel-light);font-style:italic}.cta-content p{font-size:17px;color:rgba(245,237,227,0.6);margin-bottom:var(--space-lg);max-width:480px;margin-left:auto;margin-right:auto}

/* Footer */
.footer{padding:var(--space-xl) 0 var(--space-lg);border-top:1px solid var(--light-line)}.footer-inner{max-width:var(--max-w);margin:0 auto;padding:0 var(--space-md);display:grid;grid-template-columns:2fr 1fr 1fr 1fr;gap:var(--space-lg)}.footer-brand p{font-size:14px;color:var(--warm-gray);margin-top:var(--space-xs);max-width:280px;line-height:1.65}.footer-col h4{font-size:13px;font-weight:700;text-transform:uppercase;letter-spacing:0.08em;margin-bottom:var(--space-sm)}.footer-col a{display:block;font-size:14px;color:var(--warm-gray);margin-bottom:10px;transition:color .2s;cursor:pointer}.footer-col a:hover{color:var(--espresso)}
.footer-bottom{max-width:var(--max-w);margin:var(--space-lg) auto 0;padding:var(--space-sm) var(--space-md) 0;border-top:1px solid var(--light-line);display:flex;justify-content:space-between;align-items:center;font-size:13px;color:var(--warm-gray)}

/* Mobile Menu */
.mobile-menu{display:none;position:fixed;inset:0;z-index:999;background:var(--latte);flex-direction:column;align-items:center;justify-content:center;gap:var(--space-md);opacity:0;pointer-events:none;transition:opacity .3s}.mobile-menu.active{opacity:1;pointer-events:all}.mobile-menu a{font-family:var(--font-display);font-size:28px;color:var(--espresso);cursor:pointer}.mobile-close{position:absolute;top:20px;right:24px;background:none;font-size:28px;color:var(--espresso);border:none;cursor:pointer}

/* Auth (Owner only) */
.auth-wrapper{min-height:100vh;display:flex;align-items:center;justify-content:center;padding:100px var(--space-md) var(--space-xl)}
.auth-card{width:100%;max-width:460px;background:var(--steam);border:1px solid var(--light-line);border-radius:20px;padding:var(--space-xl) var(--space-lg);box-shadow:0 16px 64px rgba(26,18,9,0.06);animation:authUp .5s cubic-bezier(0.16,1,0.3,1) both}
@keyframes authUp{from{opacity:0;transform:translateY(24px)}to{opacity:1;transform:translateY(0)}}
.auth-card h2{font-family:var(--font-display);font-size:28px;text-align:center;margin-bottom:6px}.auth-card .auth-subtitle{text-align:center;font-size:15px;color:var(--warm-gray);margin-bottom:var(--space-lg)}
.form-group{margin-bottom:var(--space-sm)}.form-label{display:block;font-size:13px;font-weight:600;margin-bottom:6px;color:var(--charcoal)}
.form-input{width:100%;padding:14px 16px;border:1.5px solid var(--light-line);border-radius:var(--radius-sm);font-size:15px;font-family:var(--font-body);background:var(--latte);transition:border-color .25s,box-shadow .25s;color:var(--espresso);outline:none}.form-input:focus{border-color:var(--caramel);box-shadow:0 0 0 3px rgba(200,133,59,0.12)}
.form-error{font-size:12px;color:var(--danger);margin-top:4px;display:none}.form-error.show{display:block}
.form-row{display:grid;grid-template-columns:1fr 1fr;gap:var(--space-sm)}
.form-helper{text-align:right;margin-top:8px;margin-bottom:var(--space-sm)}.form-helper a{font-size:13px;color:var(--caramel);font-weight:500;cursor:pointer}.form-helper a:hover{text-decoration:underline}
.form-divider{display:flex;align-items:center;gap:var(--space-sm);margin:var(--space-md) 0;color:var(--warm-gray);font-size:13px}.form-divider::before,.form-divider::after{content:'';flex:1;height:1px;background:var(--light-line)}
.form-footer{text-align:center;margin-top:var(--space-md);font-size:14px;color:var(--warm-gray)}.form-footer a{color:var(--caramel);font-weight:600;cursor:pointer}.form-footer a:hover{text-decoration:underline}
.social-btn{width:100%;padding:14px;border-radius:100px;font-size:15px;font-weight:600;display:flex;align-items:center;justify-content:center;gap:10px;background:var(--steam);border:1.5px solid var(--light-line);color:var(--espresso);cursor:pointer;transition:all .25s;margin-bottom:10px}.social-btn:hover{border-color:var(--espresso);background:rgba(26,18,9,0.02)}
.auth-success-icon{width:64px;height:64px;border-radius:50%;background:var(--success-bg);color:var(--success);display:flex;align-items:center;justify-content:center;font-size:28px;margin:0 auto var(--space-md)}
.password-toggle{position:relative}.password-toggle .toggle-eye{position:absolute;right:14px;top:50%;transform:translateY(-50%);background:none;border:none;color:var(--warm-gray);cursor:pointer;font-size:16px;padding:4px}

/* Dashboard */
.dash-layout{display:flex;min-height:100vh;padding-top:72px}
.dash-sidebar{width:260px;background:var(--steam);border-right:1px solid var(--light-line);padding:var(--space-md);position:fixed;top:72px;bottom:0;left:0;overflow-y:auto;z-index:50}
.dash-sidebar-nav{display:flex;flex-direction:column;gap:4px}
.dash-sidebar-item{display:flex;align-items:center;gap:12px;padding:12px 16px;border-radius:var(--radius-sm);font-size:14px;font-weight:500;color:var(--warm-gray);cursor:pointer;transition:all .2s;border:none;background:none;width:100%;text-align:left}.dash-sidebar-item:hover{background:var(--latte);color:var(--espresso)}.dash-sidebar-item.active{background:rgba(200,133,59,0.1);color:var(--caramel);font-weight:600}
.dash-sidebar-item .dash-icon{width:20px;text-align:center;font-size:16px}
.dash-sidebar-section{font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:0.08em;color:var(--warm-gray);padding:var(--space-md) 16px var(--space-xs)}
.dash-main{flex:1;margin-left:260px;padding:var(--space-lg);min-height:calc(100vh - 72px)}
.dash-page-title{font-family:var(--font-display);font-size:28px;margin-bottom:4px}.dash-page-desc{font-size:15px;color:var(--warm-gray);margin-bottom:var(--space-lg)}
.stats-row{display:grid;grid-template-columns:repeat(4,1fr);gap:var(--space-sm);margin-bottom:var(--space-lg)}
.stat-card{background:var(--steam);border:1px solid var(--light-line);border-radius:var(--radius);padding:var(--space-md);transition:transform .3s}.stat-card:hover{transform:translateY(-2px)}.stat-card-icon{font-size:20px;margin-bottom:var(--space-xs)}.stat-card-value{font-family:var(--font-display);font-size:32px;letter-spacing:-0.02em}.stat-card-label{font-size:13px;color:var(--warm-gray);margin-top:2px}.stat-card-change{font-size:12px;font-weight:600;margin-top:6px}.stat-card-change.up{color:var(--success)}
.dash-card{background:var(--steam);border:1px solid var(--light-line);border-radius:var(--radius);padding:var(--space-md);margin-bottom:var(--space-md)}.dash-card-header{display:flex;justify-content:space-between;align-items:center;margin-bottom:var(--space-md)}.dash-card-title{font-family:var(--font-display);font-size:20px}
.data-table{width:100%;border-collapse:collapse}.data-table th{text-align:left;font-size:12px;font-weight:700;text-transform:uppercase;letter-spacing:0.06em;color:var(--warm-gray);padding:12px 16px;border-bottom:2px solid var(--light-line)}.data-table td{padding:14px 16px;border-bottom:1px solid var(--light-line);font-size:14px}.data-table tr:hover td{background:rgba(200,133,59,0.03)}
.badge{display:inline-block;padding:3px 10px;border-radius:100px;font-size:11px;font-weight:700}.badge-active{background:var(--success-bg);color:var(--success)}.badge-paused{background:#FFF3E0;color:#E65100}.badge-owner{background:rgba(200,133,59,0.15);color:var(--mocha)}.badge-l2{background:var(--info-bg);color:var(--info)}.badge-l1{background:var(--latte);color:var(--warm-gray)}
.chart-placeholder{height:260px;background:var(--latte);border-radius:var(--radius-sm);display:flex;align-items:flex-end;justify-content:center;gap:8px;padding:var(--space-md)}
.chart-bar{width:32px;border-radius:6px 6px 0 0;transition:height .6s cubic-bezier(0.16,1,0.3,1)}.chart-bar.primary{background:var(--caramel)}

/* Scan */
.scan-interface{max-width:500px;margin:0 auto;text-align:center}
.scan-area{width:280px;height:280px;margin:0 auto var(--space-lg);background:var(--espresso);border-radius:24px;display:flex;align-items:center;justify-content:center;position:relative;overflow:hidden;cursor:pointer}
.scan-crosshair{width:180px;height:180px;position:relative}.scan-crosshair::before,.scan-crosshair::after{content:'';position:absolute;border:3px solid var(--caramel)}.scan-crosshair::before{top:0;left:0;width:40px;height:40px;border-right:none;border-bottom:none;border-radius:4px 0 0 0}.scan-crosshair::after{bottom:0;right:0;width:40px;height:40px;border-left:none;border-top:none;border-radius:0 0 4px 0}
.scan-corner-tr,.scan-corner-bl{position:absolute;border:3px solid var(--caramel);width:40px;height:40px}.scan-corner-tr{top:0;right:0;border-left:none;border-bottom:none;border-radius:0 4px 0 0}.scan-corner-bl{bottom:0;left:0;border-right:none;border-top:none;border-radius:0 0 0 4px}
.scan-line{position:absolute;left:10%;width:80%;height:2px;background:var(--caramel);box-shadow:0 0 12px var(--caramel);animation:scanLine 2.5s ease-in-out infinite}
@keyframes scanLine{0%,100%{top:20%}50%{top:80%}}
.scan-result{background:var(--steam);border:1px solid var(--light-line);border-radius:var(--radius);padding:var(--space-lg);display:none;animation:authUp .4s ease both}.scan-result.show{display:block}
.scan-result-avatar{width:60px;height:60px;border-radius:50%;margin:0 auto var(--space-sm);display:flex;align-items:center;justify-content:center;font-size:24px;font-weight:700;color:var(--steam)}
.scan-result h3{font-family:var(--font-display);font-size:22px;margin-bottom:4px}.scan-result p{font-size:14px;color:var(--warm-gray);margin-bottom:var(--space-md)}
.scan-stamp-preview{display:flex;justify-content:center;gap:8px;margin-bottom:var(--space-md)}
.scan-stamp-dot{width:28px;height:28px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:12px}.scan-stamp-dot.filled{background:var(--caramel);color:var(--steam)}.scan-stamp-dot.empty{background:var(--latte);border:1.5px solid var(--light-line)}.scan-stamp-dot.new{background:var(--caramel);color:var(--steam);animation:stampPop .4s cubic-bezier(0.34,1.56,0.64,1) both}
@keyframes stampPop{from{transform:scale(0)}to{transform:scale(1)}}

/* Customer Stamp Page (no account, accessed via unique URL) */
.customer-page{min-height:100vh;padding:40px var(--space-md);display:flex;flex-direction:column;align-items:center}
.customer-stamp-card{width:100%;max-width:400px;border-radius:24px;padding:var(--space-lg);color:var(--steam);position:relative;overflow:hidden;margin-bottom:var(--space-md)}
.customer-stamp-card::before{content:'';position:absolute;inset:0;background:url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");opacity:0.04;pointer-events:none}
.customer-cafe-name{font-family:var(--font-display);font-size:24px;margin-bottom:var(--space-xs)}
.customer-cafe-tagline{font-size:13px;opacity:.7;margin-bottom:var(--space-lg)}
.customer-stamps-grid{display:grid;grid-template-columns:repeat(5,1fr);gap:12px;margin-bottom:var(--space-md)}
.customer-stamp{aspect-ratio:1;border-radius:50%;background:rgba(255,255,255,0.15);display:flex;align-items:center;justify-content:center;font-size:20px;transition:all .3s}.customer-stamp.collected{background:rgba(255,255,255,0.9);animation:stampPop .4s cubic-bezier(0.34,1.56,0.64,1) both}
.customer-progress-bar{height:6px;background:rgba(255,255,255,0.15);border-radius:100px;margin-bottom:8px;overflow:hidden}.customer-progress-fill{height:100%;background:var(--steam);border-radius:100px;transition:width .8s cubic-bezier(0.16,1,0.3,1)}
.customer-progress-text{font-size:14px;opacity:.8;text-align:center}
.customer-reward-banner{width:100%;max-width:400px;background:var(--steam);border:2px solid var(--success);border-radius:var(--radius);padding:var(--space-md);text-align:center;animation:authUp .5s .2s both}
.customer-reward-banner h3{font-family:var(--font-display);font-size:20px;color:var(--success);margin-bottom:4px}

/* Success Overlay */
.success-overlay{position:fixed;inset:0;background:rgba(26,18,9,0.5);backdrop-filter:blur(8px);display:none;align-items:center;justify-content:center;z-index:2000}.success-overlay.show{display:flex}
.success-modal{background:var(--steam);border-radius:24px;padding:var(--space-xl);text-align:center;max-width:400px;width:90%;animation:authUp .4s cubic-bezier(0.16,1,0.3,1) both}
.success-check{width:72px;height:72px;border-radius:50%;background:var(--success-bg);color:var(--success);display:flex;align-items:center;justify-content:center;font-size:32px;margin:0 auto var(--space-md);animation:checkPop .5s cubic-bezier(0.34,1.56,0.64,1) .2s both}
@keyframes checkPop{from{transform:scale(0)}to{transform:scale(1)}}

/* Responsive */
@media(max-width:1024px){.hero-inner{grid-template-columns:1fr;text-align:center}.hero-sub{margin-left:auto;margin-right:auto}.hero-buttons{justify-content:center}.hero-visual{margin-top:var(--space-lg)}.float-badge{display:none}.features-grid{grid-template-columns:repeat(2,1fr)}.how-tracks{grid-template-columns:1fr}.pricing-grid{grid-template-columns:repeat(2,1fr)}.pricing-card:last-child{grid-column:span 2;max-width:400px;margin:0 auto}.footer-inner{grid-template-columns:1fr 1fr}.stats-row{grid-template-columns:repeat(2,1fr)}.dash-sidebar{display:none}.dash-main{margin-left:0}}
@media(max-width:768px){.nav-links{display:none}.nav-mobile-toggle{display:flex}.mobile-menu{display:flex}.features-grid{grid-template-columns:1fr}.pricing-grid{grid-template-columns:1fr}.pricing-card:last-child{grid-column:span 1;max-width:none}.cta-box{padding:var(--space-xl) var(--space-md)}.footer-inner{grid-template-columns:1fr;gap:var(--space-md)}.footer-bottom{flex-direction:column;gap:var(--space-xs);text-align:center}.phone-mockup{width:240px;height:480px}.auth-card{padding:var(--space-lg) var(--space-md)}.form-row{grid-template-columns:1fr}.stats-row{grid-template-columns:1fr}}
</style>
</head>
<body>

<!-- NAV -->
<nav class="nav" id="nav"><div class="nav-inner">
  <a class="nav-logo" onclick="navigate('landing')">brew<span>istan</span></a>
  <div class="nav-links" id="navPublic"><a onclick="navigateSection('features')">Features</a><a onclick="navigateSection('how-it-works')">How It Works</a><a onclick="navigateSection('pricing')">Pricing</a><a class="nav-cta" onclick="navigate('signup')">Get Started Free →</a></div>
  <div class="nav-user-menu" id="navUser" style="display:none"><span class="nav-user-name" id="navUserName"></span><div class="nav-avatar" id="navAvatar" onclick="navigate('dashboard')"></div><button class="nav-logout" onclick="logout()">Log Out</button></div>
  <button class="nav-mobile-toggle" onclick="document.getElementById('mobileMenu').classList.add('active')" aria-label="Menu"><span></span><span></span><span></span></button>
</div></nav>

<div class="mobile-menu" id="mobileMenu"><button class="mobile-close" onclick="this.parentElement.classList.remove('active')">✕</button><a onclick="closeMobileAndGo('features')">Features</a><a onclick="closeMobileAndGo('how-it-works')">How It Works</a><a onclick="closeMobileAndGo('pricing')">Pricing</a><a onclick="closeMobileAndNav('signup')" class="btn-primary" style="margin-top:16px">Get Started Free →</a></div>

<div class="success-overlay" id="successOverlay"><div class="success-modal"><div class="success-check">✓</div><h2 id="successTitle" style="font-family:var(--font-display);font-size:24px;margin-bottom:8px"></h2><p id="successMsg" style="color:var(--warm-gray);font-size:15px;margin-bottom:24px"></p><button class="btn-primary btn-block" onclick="closeSuccess()">Continue</button></div></div>

<!-- ======= LANDING ======= -->
<div class="page active" id="page-landing" data-page="landing">
<section class="hero"><div class="hero-inner">
  <div class="hero-text">
    <div class="hero-badge reveal">Now in Early Access</div>
    <h1 class="reveal reveal-delay-1">Turn every cup into a <em>comeback</em></h1>
    <p class="hero-sub reveal reveal-delay-2">Brewistan replaces paper punch cards with a beautiful digital loyalty system. Help your café build habit, drive repeat visits, and know your customers by name.</p>
    <div class="hero-buttons reveal reveal-delay-3"><a class="btn-primary" onclick="navigate('signup')">Start Free for Your Café →</a><a onclick="navigateSection('how-it-works')" class="btn-secondary">See How It Works</a></div>
  </div>
  <div class="hero-visual reveal reveal-delay-2">
    <div class="phone-mockup"><div class="phone-screen"><div class="phone-notch"></div><div class="phone-content">
      <p class="phone-greeting">Good morning</p><p class="phone-user">Sara ☕</p>
      <div class="phone-card"><p class="phone-card-name">Brewistan Coffee</p><div class="phone-stamps"><div class="phone-stamp filled">☕</div><div class="phone-stamp filled">☕</div><div class="phone-stamp filled">☕</div><div class="phone-stamp filled">☕</div><div class="phone-stamp filled">☕</div><div class="phone-stamp filled">☕</div><div class="phone-stamp"></div><div class="phone-stamp"></div><div class="phone-stamp"></div><div class="phone-stamp"></div></div><p class="phone-progress-text">6 of 10 — 4 more for a free coffee!</p></div>
      <div class="phone-reward-card"><div class="phone-reward-icon">🎁</div><div class="phone-reward-info"><p class="phone-reward-title">Reward Ready!</p><p class="phone-reward-desc">Free pastry at Bean & Gone</p></div></div>
    </div></div></div>
    <div class="float-badge float-badge-1"><div class="float-icon green">✓</div>Stamp collected!</div>
    <div class="float-badge float-badge-2"><div class="float-icon amber">🏆</div>+2,400 visits today</div>
  </div>
</div></section>

<section class="features" id="features"><div class="container">
  <div class="features-header"><div class="section-label reveal">Features</div><h2 class="section-title reveal reveal-delay-1">Everything your café needs</h2><p class="section-sub reveal reveal-delay-2">From a single espresso bar to a 20-location chain — Brewistan scales with you.</p></div>
  <div class="features-grid">
    <div class="feature-card reveal"><div class="feature-icon warm">📱</div><h3>QR Stamp Collection</h3><p>Customers scan, stamps appear. No paper cards, no forgotten wallets. Time-limited rotating QR tokens prevent fraud.</p></div>
    <div class="feature-card reveal reveal-delay-1"><div class="feature-icon green">🏢</div><h3>Multi-Location Chains</h3><p>One card across all your branches. A stamp at Branch 3 counts the same as Branch 7. Unified branding, unified data.</p></div>
    <div class="feature-card reveal reveal-delay-2"><div class="feature-icon blue">🎯</div><h3>Campaign Engine</h3><p>Build campaigns with a visual rule builder — happy hours, double stamps, birthday rewards, limited-time promos.</p></div>
    <div class="feature-card reveal reveal-delay-3"><div class="feature-icon purple">👥</div><h3>Role-Based Staff Access</h3><p>Owner, Shift Lead, and Barista tiers. Control who scans, who builds campaigns, and who sees analytics — per location.</p></div>
    <div class="feature-card reveal reveal-delay-4"><div class="feature-icon red">🔔</div><h3>Smart Notifications</h3><p>Bring customers back with transactional alerts, campaign launches, proximity reminders, and win-back messages.</p></div>
    <div class="feature-card reveal"><div class="feature-icon teal">📊</div><h3>Real-Time Analytics</h3><p>Stamps issued, redemption rates, top customers, location comparisons — all in a live dashboard.</p></div>
  </div>
</div></section>

<section class="how-it-works" id="how-it-works"><div class="container">
  <div class="how-header"><div class="section-label reveal" style="color:var(--caramel-light)">How It Works</div><h2 class="section-title reveal reveal-delay-1" style="color:var(--crema)">Live in minutes, not months</h2><p class="section-sub reveal reveal-delay-2">Two simple paths — one for café owners, one for coffee lovers.</p></div>
  <div class="how-tracks">
    <div class="how-track reveal"><div class="how-track-label owner">For Café Owners</div><div class="how-steps"><div class="how-step"><div class="how-step-num">1</div><div class="how-step-text"><h4>Create Your Account</h4><p>Sign up free. Add your café name, logo, and location in under two minutes.</p></div></div><div class="how-step"><div class="how-step-num">2</div><div class="how-step-text"><h4>Design Your Stamp Card</h4><p>Pick your reward threshold, choose icons, set your brand colors.</p></div></div><div class="how-step"><div class="how-step-num">3</div><div class="how-step-text"><h4>Invite Your Staff</h4><p>Add baristas with the right access level. They scan — you manage.</p></div></div><div class="how-step"><div class="how-step-num">4</div><div class="how-step-text"><h4>Watch Loyalty Grow</h4><p>Track stamps, redemptions, and repeat visits in your live dashboard.</p></div></div></div></div>
    <div class="how-track reveal reveal-delay-2"><div class="how-track-label customer">For Customers</div><div class="how-steps"><div class="how-step"><div class="how-step-num">1</div><div class="how-step-text"><h4>Buy Your Coffee</h4><p>Order at the counter like normal. No app download required.</p></div></div><div class="how-step"><div class="how-step-num">2</div><div class="how-step-text"><h4>Scan the QR Code</h4><p>The barista scans your unique QR — or you scan theirs. Stamp appears instantly.</p></div></div><div class="how-step"><div class="how-step-num">3</div><div class="how-step-text"><h4>Track on Any Device</h4><p>Your stamp card lives on a web page — add it to your home screen to never lose it.</p></div></div><div class="how-step"><div class="how-step-num">4</div><div class="how-step-text"><h4>Redeem Your Reward</h4><p>Hit the target and your reward unlocks. Show your screen — done.</p></div></div></div></div>
  </div>
</div></section>

<section class="pricing" id="pricing"><div class="container">
  <div class="pricing-header"><div class="section-label reveal">Pricing</div><h2 class="section-title reveal reveal-delay-1">Simple, transparent plans</h2><p class="section-sub reveal reveal-delay-2">Start free. Upgrade when you're ready. No hidden fees, no contracts.</p></div>
  <div class="pricing-grid">
    <div class="pricing-card reveal"><div class="pricing-tier">Free</div><div class="pricing-price">$0 <span>/ month</span></div><p class="pricing-desc">Perfect for a single café just getting started with digital loyalty.</p><ul class="pricing-features"><li>1 location</li><li>1 active campaign</li><li>Up to 200 customers</li><li>Basic stamp analytics</li><li>QR code scanning</li></ul><a onclick="navigate('signup')" class="pricing-btn outline">Get Started</a></div>
    <div class="pricing-card featured reveal reveal-delay-1"><div class="pricing-tier">Pro</div><div class="pricing-price">$59 <span>/ month</span></div><p class="pricing-desc">For growing cafés that want campaigns, notifications, and deeper insights.</p><ul class="pricing-features"><li>Up to 5 locations</li><li>10 active campaigns</li><li>Unlimited customers</li><li>10 push notifications / month</li><li>Full analytics dashboard</li><li>Role-based staff access</li></ul><a onclick="navigate('signup')" class="pricing-btn primary">Start 14-Day Trial</a></div>
    <div class="pricing-card reveal reveal-delay-2"><div class="pricing-tier">Enterprise</div><div class="pricing-price">Custom</div><p class="pricing-desc">For chains and franchises that need full control, API access, and dedicated support.</p><ul class="pricing-features"><li>Unlimited locations</li><li>POS integration (Square, Toast)</li><li>API access</li><li>Dedicated account manager</li><li>Custom stamp card designs</li><li>SLA & priority support</li></ul><a onclick="navigate('signup')" class="pricing-btn outline">Contact Sales</a></div>
  </div>
</div></section>

<section class="cta" id="cta"><div class="container"><div class="cta-box reveal"><div class="cta-content"><h2>Ready to turn cups into <em>comebacks?</em></h2><p>Join cafés already building loyalty with Brewistan. Free to start, takes two minutes, no credit card required.</p><button class="btn-cta-light" onclick="navigate('signup')">Create Your Free Account →</button></div></div></div></section>

<footer class="footer"><div class="footer-inner"><div class="footer-brand"><a class="nav-logo" style="font-size:22px" onclick="navigate('landing')">brew<span>istan</span></a><p>Digital loyalty for independent cafés and chains. Replace paper punch cards with something your customers will actually use.</p></div><div class="footer-col"><h4>Product</h4><a onclick="navigateSection('features')">Features</a><a onclick="navigateSection('pricing')">Pricing</a><a onclick="navigateSection('how-it-works')">How It Works</a><a>API Docs</a></div><div class="footer-col"><h4>Company</h4><a>About</a><a>Blog</a><a>Careers</a><a>Contact</a></div><div class="footer-col"><h4>Legal</h4><a>Privacy Policy</a><a>Terms of Service</a><a>Cookie Policy</a></div></div><div class="footer-bottom"><span>© 2026 Brewistan. All rights reserved.</span><span>Made with ☕ for coffee lovers everywhere</span></div></footer>
</div>

<!-- ======= SIGN UP (Owner Only) ======= -->
<div class="page" id="page-signup" data-page="signup"><div class="auth-wrapper"><div class="auth-card">
  <h2>Open your café account</h2>
  <p class="auth-subtitle">Set up your digital stamp card in 2 minutes</p>
  <form id="signupForm" onsubmit="handleSignup(event)">
    <div class="form-row"><div class="form-group"><label class="form-label">First Name</label><input class="form-input" type="text" id="signupFirst" placeholder="Mustafa" required></div><div class="form-group"><label class="form-label">Last Name</label><input class="form-input" type="text" id="signupLast" placeholder="Al-Rawi" required></div></div>
    <div class="form-group"><label class="form-label">Café Name</label><input class="form-input" type="text" id="signupCafe" placeholder="My Awesome Café" required></div>
    <div class="form-group"><label class="form-label">Email</label><input class="form-input" type="email" id="signupEmail" placeholder="mustafa@mycafe.com" required></div>
    <div class="form-group"><label class="form-label">Phone Number</label><input class="form-input" type="tel" id="signupPhone" placeholder="+964 XXX XXX XXXX"></div>
    <div class="form-group"><label class="form-label">Password</label><div class="password-toggle"><input class="form-input" type="password" id="signupPassword" placeholder="Min 8 characters" required minlength="8"><button type="button" class="toggle-eye" onclick="togglePassword('signupPassword',this)">👁</button></div><div class="form-error" id="signupPassError">Password must be at least 8 characters</div></div>
    <div class="form-group"><label class="form-label">Confirm Password</label><input class="form-input" type="password" id="signupConfirm" placeholder="Re-enter password" required><div class="form-error" id="signupConfirmError">Passwords do not match</div></div>
    <button type="submit" class="btn-primary btn-block" style="margin-top:var(--space-md)">Create Café Account →</button>
  </form>
  <div class="form-divider">or continue with</div>
  <button class="social-btn" onclick="handleSocialAuth('google')"><svg width="18" height="18" viewBox="0 0 24 24"><path d="M22.56 12.25c0-.78-.07-1.53-.2-2.25H12v4.26h5.92a5.06 5.06 0 01-2.2 3.32v2.77h3.57c2.08-1.92 3.28-4.74 3.28-8.1z" fill="#4285F4"/><path d="M12 23c2.97 0 5.46-.98 7.28-2.66l-3.57-2.77c-.98.66-2.23 1.06-3.71 1.06-2.86 0-5.29-1.93-6.16-4.53H2.18v2.84C3.99 20.53 7.7 23 12 23z" fill="#34A853"/><path d="M5.84 14.09c-.22-.66-.35-1.36-.35-2.09s.13-1.43.35-2.09V7.07H2.18C1.43 8.55 1 10.22 1 12s.43 3.45 1.18 4.93l2.85-2.22.81-.62z" fill="#FBBC05"/><path d="M12 5.38c1.62 0 3.06.56 4.21 1.64l3.15-3.15C17.45 2.09 14.97 1 12 1 7.7 1 3.99 3.47 2.18 7.07l3.66 2.84c.87-2.6 3.3-4.53 6.16-4.53z" fill="#EA4335"/></svg>Continue with Google</button>
  <div class="form-footer">Already have an account? <a onclick="navigate('login')">Log In</a></div>
</div></div></div>

<!-- ======= LOGIN (Owner Only) ======= -->
<div class="page" id="page-login" data-page="login"><div class="auth-wrapper"><div class="auth-card">
  <h2>Welcome back</h2><p class="auth-subtitle">Log in to manage your café</p>
  <form id="loginForm" onsubmit="handleLogin(event)">
    <div class="form-group"><label class="form-label">Email</label><input class="form-input" type="email" id="loginEmail" placeholder="mustafa@mycafe.com" required></div>
    <div class="form-group"><label class="form-label">Password</label><div class="password-toggle"><input class="form-input" type="password" id="loginPassword" placeholder="Enter your password" required><button type="button" class="toggle-eye" onclick="togglePassword('loginPassword',this)">👁</button></div></div>
    <div class="form-helper"><a onclick="navigate('forgot-password')">Forgot password?</a></div>
    <button type="submit" class="btn-primary btn-block">Log In →</button>
  </form>
  <div class="form-divider">or continue with</div>
  <button class="social-btn" onclick="handleSocialAuth('google')"><svg width="18" height="18" viewBox="0 0 24 24"><path d="M22.56 12.25c0-.78-.07-1.53-.2-2.25H12v4.26h5.92a5.06 5.06 0 01-2.2 3.32v2.77h3.57c2.08-1.92 3.28-4.74 3.28-8.1z" fill="#4285F4"/><path d="M12 23c2.97 0 5.46-.98 7.28-2.66l-3.57-2.77c-.98.66-2.23 1.06-3.71 1.06-2.86 0-5.29-1.93-6.16-4.53H2.18v2.84C3.99 20.53 7.7 23 12 23z" fill="#34A853"/><path d="M5.84 14.09c-.22-.66-.35-1.36-.35-2.09s.13-1.43.35-2.09V7.07H2.18C1.43 8.55 1 10.22 1 12s.43 3.45 1.18 4.93l2.85-2.22.81-.62z" fill="#FBBC05"/><path d="M12 5.38c1.62 0 3.06.56 4.21 1.64l3.15-3.15C17.45 2.09 14.97 1 12 1 7.7 1 3.99 3.47 2.18 7.07l3.66 2.84c.87-2.6 3.3-4.53 6.16-4.53z" fill="#EA4335"/></svg>Continue with Google</button>
  <div class="form-footer">Don't have a café account? <a onclick="navigate('signup')">Sign Up Free</a></div>
</div></div></div>

<!-- ======= FORGOT PASSWORD ======= -->
<div class="page" id="page-forgot-password" data-page="forgot-password"><div class="auth-wrapper">
  <div class="auth-card" id="forgotStep1"><h2>Reset your password</h2><p class="auth-subtitle">Enter your email and we'll send you a reset link</p>
    <form onsubmit="handleForgotPassword(event)"><div class="form-group"><label class="form-label">Email Address</label><input class="form-input" type="email" id="forgotEmail" placeholder="mustafa@mycafe.com" required></div><button type="submit" class="btn-primary btn-block" style="margin-top:var(--space-md)">Send Reset Link →</button></form>
    <div class="form-footer" style="margin-top:var(--space-md)"><a onclick="navigate('login')">← Back to Log In</a></div>
  </div>
  <div class="auth-card" id="forgotStep2" style="display:none"><div class="auth-success-icon">✉️</div><h2>Check your inbox</h2><p class="auth-subtitle">We've sent a password reset link to <strong id="forgotSentEmail"></strong></p>
    <button class="btn-primary btn-block" onclick="navigate('reset-password')" style="margin-top:var(--space-md)">Enter Reset Code →</button>
    <div class="form-footer" style="margin-top:var(--space-md)">Didn't receive it? <a onclick="document.getElementById('forgotStep2').style.display='none';document.getElementById('forgotStep1').style.display='block'">Resend</a></div>
  </div>
</div></div>

<!-- ======= RESET PASSWORD ======= -->
<div class="page" id="page-reset-password" data-page="reset-password"><div class="auth-wrapper"><div class="auth-card">
  <h2>Create new password</h2><p class="auth-subtitle">Enter the code from your email and choose a new password</p>
  <form onsubmit="handleResetPassword(event)">
    <div class="form-group"><label class="form-label">Reset Code</label><input class="form-input" type="text" id="resetCode" placeholder="000000" required maxlength="6" style="letter-spacing:8px;text-align:center;font-size:20px;font-weight:700"></div>
    <div class="form-group"><label class="form-label">New Password</label><div class="password-toggle"><input class="form-input" type="password" id="resetNewPass" placeholder="Min 8 characters" required minlength="8"><button type="button" class="toggle-eye" onclick="togglePassword('resetNewPass',this)">👁</button></div></div>
    <div class="form-group"><label class="form-label">Confirm New Password</label><input class="form-input" type="password" id="resetConfirmPass" placeholder="Re-enter password" required><div class="form-error" id="resetConfirmError">Passwords do not match</div></div>
    <button type="submit" class="btn-primary btn-block" style="margin-top:var(--space-md)">Reset Password →</button>
  </form>
</div></div></div>

<!-- ======= OWNER DASHBOARD ======= -->
<div class="page" id="page-dashboard" data-page="dashboard"><div class="dash-layout">
  <aside class="dash-sidebar">
    <div class="dash-sidebar-section">Main</div>
    <nav class="dash-sidebar-nav">
      <button class="dash-sidebar-item active" onclick="switchTab('overview',this)"><span class="dash-icon">📊</span>Overview</button>
      <button class="dash-sidebar-item" onclick="switchTab('campaigns',this)"><span class="dash-icon">🎯</span>Campaigns</button>
      <button class="dash-sidebar-item" onclick="switchTab('staff',this)"><span class="dash-icon">👥</span>Staff</button>
      <button class="dash-sidebar-item" onclick="switchTab('scan',this)"><span class="dash-icon">📱</span>Scan</button>
    </nav>
    <div class="dash-sidebar-section">Settings</div>
    <nav class="dash-sidebar-nav">
      <button class="dash-sidebar-item" onclick="switchTab('locations',this)"><span class="dash-icon">📍</span>Locations</button>
      <button class="dash-sidebar-item" onclick="switchTab('settings',this)"><span class="dash-icon">⚙️</span>Settings</button>
    </nav>
  </aside>
  <main class="dash-main">
    <!-- Overview -->
    <div id="tab-overview">
      <h1 class="dash-page-title" id="dashGreeting">Dashboard</h1><p class="dash-page-desc">Welcome back! Here's how your café is doing.</p>
      <div class="stats-row">
        <div class="stat-card"><div class="stat-card-icon">☕</div><div class="stat-card-value">1,284</div><div class="stat-card-label">Total Stamps</div><div class="stat-card-change up">↑ 18% this week</div></div>
        <div class="stat-card"><div class="stat-card-icon">👥</div><div class="stat-card-value">342</div><div class="stat-card-label">Active Customers</div><div class="stat-card-change up">↑ 12% this month</div></div>
        <div class="stat-card"><div class="stat-card-icon">🎁</div><div class="stat-card-value">67</div><div class="stat-card-label">Rewards Redeemed</div><div class="stat-card-change up">↑ 24% this week</div></div>
        <div class="stat-card"><div class="stat-card-icon">🔄</div><div class="stat-card-value">3.4×</div><div class="stat-card-label">Repeat Visit Rate</div><div class="stat-card-change up">↑ 0.3 vs last month</div></div>
      </div>
      <div class="dash-card"><div class="dash-card-header"><h3 class="dash-card-title">Stamps This Week</h3><span style="font-size:13px;color:var(--warm-gray)">Mon – Sun</span></div><div class="chart-placeholder" id="weeklyChart"></div></div>
      <div class="dash-card"><div class="dash-card-header"><h3 class="dash-card-title">Top Customers</h3></div><table class="data-table"><thead><tr><th>Customer</th><th>Stamps</th><th>Visits</th><th>Last Visit</th></tr></thead><tbody><tr><td><strong>Sara Ahmed</strong></td><td>46</td><td>38</td><td>Today</td></tr><tr><td><strong>Omar Hassan</strong></td><td>39</td><td>31</td><td>Yesterday</td></tr><tr><td><strong>Noor Ali</strong></td><td>34</td><td>28</td><td>2 days ago</td></tr><tr><td><strong>Yusuf Karim</strong></td><td>28</td><td>22</td><td>Today</td></tr><tr><td><strong>Layla Mustafa</strong></td><td>25</td><td>20</td><td>3 days ago</td></tr></tbody></table></div>
    </div>
    <!-- Campaigns -->
    <div id="tab-campaigns" style="display:none"><div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:var(--space-md)"><div><h1 class="dash-page-title">Campaigns</h1><p class="dash-page-desc">Create and manage your loyalty campaigns.</p></div><button class="btn-primary btn-sm" onclick="showModal('Campaign builder','This will connect to your campaign API endpoint')">+ New Campaign</button></div><div class="dash-card"><table class="data-table"><thead><tr><th>Campaign</th><th>Type</th><th>Stamps</th><th>Reward</th><th>Status</th></tr></thead><tbody><tr><td><strong>Free Coffee Classic</strong></td><td>Standard</td><td>10</td><td>Free Coffee</td><td><span class="badge badge-active">Active</span></td></tr><tr><td><strong>Double Stamp Friday</strong></td><td>Multiplier</td><td>—</td><td>2× stamps</td><td><span class="badge badge-active">Active</span></td></tr><tr><td><strong>Birthday Treat</strong></td><td>Special</td><td>1</td><td>Free Pastry</td><td><span class="badge badge-paused">Paused</span></td></tr></tbody></table></div></div>
    <!-- Staff -->
    <div id="tab-staff" style="display:none"><div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:var(--space-md)"><div><h1 class="dash-page-title">Staff</h1><p class="dash-page-desc">Manage your team and access levels.</p></div><button class="btn-primary btn-sm" onclick="showModal('Add Staff','Staff invitations will connect to your email API')">+ Invite Staff</button></div><div class="dash-card"><table class="data-table"><thead><tr><th>Name</th><th>Email</th><th>Role</th><th>Location</th><th>Scans Today</th></tr></thead><tbody><tr><td><strong id="staffOwnerName">You (Owner)</strong></td><td id="staffOwnerEmail">—</td><td><span class="badge badge-owner">Owner</span></td><td>All</td><td>—</td></tr><tr><td><strong>Ahmed R.</strong></td><td>ahmed@email.com</td><td><span class="badge badge-l2">Shift Lead</span></td><td>Downtown</td><td>34</td></tr><tr><td><strong>Fatima K.</strong></td><td>fatima@email.com</td><td><span class="badge badge-l1">Barista</span></td><td>Downtown</td><td>21</td></tr><tr><td><strong>Ali M.</strong></td><td>ali@email.com</td><td><span class="badge badge-l1">Barista</span></td><td>Mall Branch</td><td>18</td></tr></tbody></table></div></div>
    <!-- Scan -->
    <div id="tab-scan" style="display:none"><h1 class="dash-page-title" style="text-align:center">Scan Customer</h1><p class="dash-page-desc" style="text-align:center">Scan a customer's QR code to issue a stamp</p><div class="scan-interface"><div class="scan-area" id="scanArea" onclick="simulateScan()"><div class="scan-crosshair"><div class="scan-corner-tr"></div><div class="scan-corner-bl"></div></div><div class="scan-line"></div></div><p style="font-size:14px;color:var(--warm-gray);margin-bottom:var(--space-lg)">Tap the scanner to simulate a customer scan</p><div class="scan-result" id="scanResult"><div class="scan-result-avatar" style="background:var(--caramel)">S</div><h3>Sara Ahmed</h3><p id="scanStatus">Stamp 7 of 10 — 3 more for a free coffee!</p><div class="scan-stamp-preview" id="scanStamps"></div><div style="display:flex;gap:var(--space-sm)"><button class="btn-primary" style="flex:1" onclick="confirmStamp()">✓ Confirm Stamp</button><button class="btn-secondary btn-sm" style="flex:0" onclick="resetScan()">Cancel</button></div></div></div></div>
    <!-- Locations -->
    <div id="tab-locations" style="display:none"><div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:var(--space-md)"><div><h1 class="dash-page-title">Locations</h1><p class="dash-page-desc">Manage your café branches.</p></div><button class="btn-primary btn-sm">+ Add Location</button></div><div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:var(--space-md)"><div class="dash-card"><h3 style="font-family:var(--font-display);font-size:18px;margin-bottom:8px">📍 Downtown Branch</h3><p style="font-size:14px;color:var(--warm-gray);margin-bottom:12px">123 Al-Rasheed St, Baghdad</p><div style="display:flex;gap:var(--space-md);font-size:13px"><span><strong>3</strong> staff</span><span><strong>89</strong> stamps today</span><span class="badge badge-active">Open</span></div></div><div class="dash-card"><h3 style="font-family:var(--font-display);font-size:18px;margin-bottom:8px">📍 Mall Branch</h3><p style="font-size:14px;color:var(--warm-gray);margin-bottom:12px">Baghdad Mall, Level 2</p><div style="display:flex;gap:var(--space-md);font-size:13px"><span><strong>2</strong> staff</span><span><strong>54</strong> stamps today</span><span class="badge badge-active">Open</span></div></div></div></div>
    <!-- Settings -->
    <div id="tab-settings" style="display:none"><h1 class="dash-page-title">Settings</h1><p class="dash-page-desc">Manage your café profile, branding, and billing.</p>
      <div class="dash-card"><h3 class="dash-card-title" style="margin-bottom:var(--space-md)">Café Profile</h3><div class="form-row" style="margin-bottom:var(--space-sm)"><div class="form-group"><label class="form-label">Café Name</label><input class="form-input" value="Brewistan Coffee" id="settingsCafeName"></div><div class="form-group"><label class="form-label">Phone</label><input class="form-input" value="+964 770 123 4567"></div></div><div class="form-group"><label class="form-label">Address</label><input class="form-input" value="123 Al-Rasheed St, Baghdad, Iraq"></div><button class="btn-primary btn-sm" style="margin-top:var(--space-sm)">Save Changes</button></div>
      <div class="dash-card"><h3 class="dash-card-title" style="margin-bottom:var(--space-md)">Stamp Card Design</h3><div class="form-row" style="margin-bottom:var(--space-sm)"><div class="form-group"><label class="form-label">Stamps Needed</label><input class="form-input" type="number" value="10" min="3" max="20"></div><div class="form-group"><label class="form-label">Reward</label><input class="form-input" value="Free Coffee"></div></div><div class="form-group"><label class="form-label">Brand Color</label><div style="display:flex;gap:8px;margin-top:4px"><span style="width:36px;height:36px;border-radius:50%;background:var(--caramel);border:3px solid var(--espresso);cursor:pointer"></span><span style="width:36px;height:36px;border-radius:50%;background:#6B4226;cursor:pointer"></span><span style="width:36px;height:36px;border-radius:50%;background:#2E7D32;cursor:pointer"></span><span style="width:36px;height:36px;border-radius:50%;background:#1565C0;cursor:pointer"></span><span style="width:36px;height:36px;border-radius:50%;background:#D32F2F;cursor:pointer"></span></div></div><button class="btn-primary btn-sm" style="margin-top:var(--space-sm)">Update Card</button></div>
      <div class="dash-card"><h3 class="dash-card-title" style="margin-bottom:var(--space-md)">Subscription</h3><p style="font-size:15px;margin-bottom:var(--space-sm)">Current plan: <strong style="color:var(--caramel)">Free</strong></p><button class="btn-primary btn-sm btn-caramel">Upgrade to Pro — $59/mo</button></div>
    </div>
  </main>
</div></div>

<!-- ======= CUSTOMER STAMP PAGE (No account, accessed via unique link like /c/abc123) ======= -->
<div class="page" id="page-customer-stamp" data-page="customer-stamp">
  <div class="customer-page">
    <a class="nav-logo" style="font-size:22px;margin-bottom:var(--space-lg)" onclick="navigate('landing')">brew<span>istan</span></a>

    <div class="customer-stamp-card" id="customerCard" style="background:linear-gradient(135deg,#6B4226,#C8853B)">
      <div class="customer-cafe-name" id="custCafeName">Brewistan Coffee</div>
      <div class="customer-cafe-tagline" id="custCafeTagline">Collect 10 stamps, get a free coffee</div>
      <div class="customer-stamps-grid" id="custStamps"></div>
      <div class="customer-progress-bar"><div class="customer-progress-fill" id="custProgressFill" style="width:60%"></div></div>
      <div class="customer-progress-text" id="custProgressText">6 of 10 — 4 more for a free coffee!</div>
    </div>

    <div class="customer-reward-banner" id="custRewardBanner" style="display:none">
      <h3>🎁 Reward Unlocked!</h3>
      <p style="font-size:14px;color:var(--warm-gray);margin-bottom:var(--space-sm)">Show this screen to your barista to redeem</p>
      <button class="btn-primary btn-block" onclick="showSuccess('Redeemed!','Your barista will confirm. Enjoy your free coffee!',null)">Redeem Now</button>
    </div>

    <div style="max-width:400px;width:100%;margin-top:var(--space-md);text-align:center">
      <p style="font-size:13px;color:var(--warm-gray);margin-bottom:var(--space-xs)">Add to home screen to never lose your card</p>
      <p style="font-size:12px;color:var(--warm-gray);opacity:.7">Your stamps are saved on our server — they won't be lost if you clear your browser</p>
    </div>
  </div>
</div>

<script>
/* ===== API HOOKS — Replace with real fetch() calls ===== */
const API = {
  // Owner Auth
  signup: async (data) => { /* POST /api/auth/signup */ return { success: true, user: { id: 'usr_' + Date.now(), ...data } }; },
  login: async (email, pass) => { /* POST /api/auth/login */ return { success: true, token: 'tok_' + Date.now(), user: { email, cafeName: 'Brewistan Coffee' } }; },
  forgotPassword: async (email) => { /* POST /api/auth/forgot-password */ return { success: true }; },
  resetPassword: async (code, pass) => { /* POST /api/auth/reset-password */ return { success: true }; },
  socialAuth: async (provider) => { /* GET /api/auth/google */ return { success: true }; },

  // Dashboard
  getStats: async () => { /* GET /api/dashboard/stats */ return { stamps: 1284, customers: 342, redeemed: 67, repeatRate: 3.4 }; },
  getCampaigns: async () => { /* GET /api/campaigns */ return []; },
  createCampaign: async (data) => { /* POST /api/campaigns */ return { success: true }; },
  getStaff: async () => { /* GET /api/staff */ return []; },
  inviteStaff: async (data) => { /* POST /api/staff/invite */ return { success: true }; },
  getLocations: async () => { /* GET /api/locations */ return []; },
  updateSettings: async (data) => { /* PUT /api/settings */ return { success: true }; },

  // Scan (Staff/Owner uses this)
  scanCustomer: async (qrCode) => { /* POST /api/scan */ return { success: true, customer: { id: 'cust_1', name: 'Sara Ahmed', stamps: 6, totalNeeded: 10, reward: 'Free Coffee' } }; },
  confirmStamp: async (custId) => { /* POST /api/scan/confirm */ return { success: true, newStampCount: 7 }; },

  // Customer stamp page (public, no auth)
  getCustomerCard: async (cardId) => { /* GET /api/c/:cardId */ return { cafeName: 'Brewistan Coffee', stamps: 6, totalNeeded: 10, reward: 'Free Coffee', brandColor: '#C8853B' }; },
};

/* ===== STATE ===== */
let currentUser = null;

/* ===== ROUTER ===== */
function navigate(page, push = true) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active', 'visible'));
  const el = document.getElementById('page-' + page); if (!el) return;
  el.classList.add('active');
  requestAnimationFrame(() => requestAnimationFrame(() => el.classList.add('visible')));
  const isAuth = !!currentUser, isLanding = page === 'landing', isCust = page === 'customer-stamp';
  document.getElementById('navPublic').style.display = (isLanding && !isAuth) ? 'flex' : 'none';
  document.getElementById('navUser').style.display = isAuth ? 'flex' : 'none';
  const nav = document.getElementById('nav');
  isCust ? nav.style.display = 'none' : nav.style.display = '';
  page !== 'landing' ? nav.classList.add('nav-solid') : nav.classList.remove('nav-solid');
  window.scrollTo(0, 0);
  setTimeout(() => el.querySelectorAll('.reveal').forEach(r => RO.observe(r)), 100);
  if (page === 'dashboard') initDashboard();
  if (page === 'customer-stamp') initCustomerStamp();
  if (push) history.pushState({ page }, '', page === 'landing' ? '/' : '/' + page);
}
function navigateSection(id) { navigate('landing', false); setTimeout(() => { const el = document.getElementById(id); if (el) window.scrollTo({ top: el.getBoundingClientRect().top + window.pageYOffset - 80, behavior: 'smooth' }); }, 100); }
function closeMobileAndGo(id) { document.getElementById('mobileMenu').classList.remove('active'); navigateSection(id); }
function closeMobileAndNav(p) { document.getElementById('mobileMenu').classList.remove('active'); navigate(p); }
window.addEventListener('popstate', e => navigate(e.state?.page || 'landing', false));

/* ===== AUTH (Owner Only) ===== */
async function handleSignup(e) {
  e.preventDefault();
  const p = document.getElementById('signupPassword').value, c = document.getElementById('signupConfirm').value;
  if (p.length < 8) { showFieldError('signupPassError'); return; }
  if (p !== c) { showFieldError('signupConfirmError'); return; }
  const data = { firstName: document.getElementById('signupFirst').value, lastName: document.getElementById('signupLast').value, cafeName: document.getElementById('signupCafe').value, email: document.getElementById('signupEmail').value, phone: document.getElementById('signupPhone').value, password: p };
  const r = await API.signup(data);
  if (r.success) { currentUser = { name: data.firstName, email: data.email, cafeName: data.cafeName }; updateNav(); showSuccess('Welcome to Brewistan!', 'Your café account is ready. Let\'s set up your stamp card.', () => navigate('dashboard')); }
}
async function handleLogin(e) {
  e.preventDefault();
  const em = document.getElementById('loginEmail').value;
  const r = await API.login(em, document.getElementById('loginPassword').value);
  if (r.success) { currentUser = { name: em.split('@')[0], email: em, cafeName: 'Brewistan Coffee' }; updateNav(); navigate('dashboard'); }
}
async function handleForgotPassword(e) { e.preventDefault(); const em = document.getElementById('forgotEmail').value; await API.forgotPassword(em); document.getElementById('forgotSentEmail').textContent = em; document.getElementById('forgotStep1').style.display = 'none'; document.getElementById('forgotStep2').style.display = 'block'; }
async function handleResetPassword(e) { e.preventDefault(); const np = document.getElementById('resetNewPass').value, cp = document.getElementById('resetConfirmPass').value; if (np !== cp) { showFieldError('resetConfirmError'); return; } await API.resetPassword(document.getElementById('resetCode').value, np); showSuccess('Password Updated', 'You can now log in with your new password.', () => navigate('login')); }
async function handleSocialAuth(p) { await API.socialAuth(p); currentUser = { name: 'Mustafa', email: 'mustafa@mycafe.com', cafeName: 'Brewistan Coffee' }; updateNav(); navigate('dashboard'); }
function logout() { currentUser = null; navigate('landing'); }
function updateNav() { if (!currentUser) return; document.getElementById('navUserName').textContent = currentUser.name; document.getElementById('navAvatar').textContent = currentUser.name.charAt(0).toUpperCase(); }
function togglePassword(id, btn) { const i = document.getElementById(id); i.type = i.type === 'password' ? 'text' : 'password'; btn.textContent = i.type === 'password' ? '👁' : '🙈'; }
function showFieldError(id) { const el = document.getElementById(id); el.classList.add('show'); setTimeout(() => el.classList.remove('show'), 3000); }

/* ===== SUCCESS OVERLAY ===== */
let successCb = null;
function showSuccess(t, m, cb) { document.getElementById('successTitle').textContent = t; document.getElementById('successMsg').textContent = m; document.getElementById('successOverlay').classList.add('show'); successCb = cb; }
function closeSuccess() { document.getElementById('successOverlay').classList.remove('show'); if (successCb) { successCb(); successCb = null; } }
function showModal(title, msg) { showSuccess(title, msg + '. This feature will be fully functional once the backend is connected.', null); }

/* ===== DASHBOARD ===== */
function initDashboard() {
  if (currentUser) {
    document.getElementById('dashGreeting').textContent = currentUser.cafeName || 'Dashboard';
    document.getElementById('staffOwnerEmail').textContent = currentUser.email || '—';
    document.getElementById('staffOwnerName').textContent = currentUser.name + ' (Owner)';
  }
  animateChart();
}
function switchTab(tab, btn) { document.querySelectorAll('[id^="tab-"]').forEach(t => t.style.display = 'none'); document.getElementById('tab-' + tab).style.display = 'block'; document.querySelectorAll('.dash-sidebar-item').forEach(b => b.classList.remove('active')); if (btn) btn.classList.add('active'); if (tab === 'overview') animateChart(); }
function animateChart() { const c = document.getElementById('weeklyChart'); if (!c) return; const days = ['Mon','Tue','Wed','Thu','Fri','Sat','Sun'], vals = [65,80,55,90,120,140,95]; c.innerHTML = ''; days.forEach((d, i) => { const g = document.createElement('div'); g.style.cssText = 'display:flex;flex-direction:column;align-items:center;gap:4px'; const b = document.createElement('div'); b.className = 'chart-bar primary'; b.style.height = '0px'; b.style.width = '32px'; setTimeout(() => b.style.height = (vals[i]/160*200) + 'px', 100 + i * 80); const l = document.createElement('span'); l.style.cssText = 'font-size:11px;color:var(--warm-gray)'; l.textContent = d; g.appendChild(b); g.appendChild(l); c.appendChild(g); }); }

/* ===== SCAN ===== */
let scanned = false;
function simulateScan() {
  if (scanned) return; scanned = true;
  document.getElementById('scanArea').style.display = 'none';
  document.getElementById('scanResult').classList.add('show');
  const c = document.getElementById('scanStamps'); c.innerHTML = '';
  for (let i = 0; i < 10; i++) { const d = document.createElement('div'); d.className = 'scan-stamp-dot ' + (i < 6 ? 'filled' : (i === 6 ? 'new' : 'empty')); d.textContent = i < 7 ? '☕' : ''; d.style.animationDelay = (i * 0.05) + 's'; c.appendChild(d); }
}
function confirmStamp() { showSuccess('Stamp Confirmed!', 'Sara Ahmed now has 7 of 10 stamps. 3 more for a free coffee!', () => resetScan()); }
function resetScan() { scanned = false; document.getElementById('scanArea').style.display = 'flex'; document.getElementById('scanResult').classList.remove('show'); }

/* ===== CUSTOMER STAMP PAGE (public, no auth) ===== */
function initCustomerStamp() {
  // In production: const cardId = window.location.pathname.split('/c/')[1];
  // const data = await API.getCustomerCard(cardId);
  const data = { cafeName: 'Brewistan Coffee', stamps: 6, totalNeeded: 10, reward: 'Free Coffee' };
  document.getElementById('custCafeName').textContent = data.cafeName;
  document.getElementById('custCafeTagline').textContent = 'Collect ' + data.totalNeeded + ' stamps, get a ' + data.reward.toLowerCase();
  document.getElementById('custProgressFill').style.width = (data.stamps / data.totalNeeded * 100) + '%';
  document.getElementById('custProgressText').textContent = data.stamps + ' of ' + data.totalNeeded + ' — ' + (data.totalNeeded - data.stamps) + ' more for a ' + data.reward.toLowerCase() + '!';
  const g = document.getElementById('custStamps'); g.innerHTML = '';
  for (let i = 0; i < data.totalNeeded; i++) { const s = document.createElement('div'); s.className = 'customer-stamp' + (i < data.stamps ? ' collected' : ''); s.textContent = i < data.stamps ? '☕' : ''; s.style.animationDelay = (i * 0.06) + 's'; g.appendChild(s); }
  document.getElementById('custRewardBanner').style.display = data.stamps >= data.totalNeeded ? 'block' : 'none';
}

/* ===== OBSERVERS ===== */
const RO = new IntersectionObserver(e => e.forEach(en => { if (en.isIntersecting) en.target.classList.add('visible'); }), { threshold: 0.1, rootMargin: '0px 0px -40px 0px' });
document.querySelectorAll('.reveal').forEach(el => RO.observe(el));
window.addEventListener('scroll', () => { const n = document.getElementById('nav'); if (!n.classList.contains('nav-solid')) n.classList.toggle('scrolled', window.scrollY > 40); });

/* ===== INIT ===== */
(function() {
  const p = window.location.pathname.replace(/^\//, '').replace(/\/$/, '');
  const valid = ['landing','signup','login','forgot-password','reset-password','dashboard','customer-stamp'];
  // Handle /c/xxx customer card URLs
  if (p.startsWith('c/')) { navigate('customer-stamp', false); return; }
  navigate(valid.includes(p) ? p : 'landing', false);
})();
</script>
</body>
</html>
