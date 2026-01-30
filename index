export default {
  async fetch(request) {
    const url = new URL(request.url);

    const proxyTarget = url.searchParams.get('proxy');
  
    if (proxyTarget === 'openai') {
      const proxyUrl = new URL(url.pathname + url.search, 'https://api.openai.com');
      proxyUrl.searchParams.delete('proxy');
      return fetch(proxyUrl, { headers: request.headers, method: request.method, body: request.body });
    }
    
    if (proxyTarget === 'wuyinkeji') {
      const proxyUrl = new URL(url.pathname + url.search, 'https://api.wuyinkeji.com');
      proxyUrl.searchParams.delete('proxy');
      return fetch(proxyUrl, { headers: request.headers, method: request.method, body: request.body });
    }

    if (proxyTarget === 'openrouter') {
      const proxyUrl = new URL(url.pathname + url.search, 'https://openrouter.ai');
      proxyUrl.searchParams.delete('proxy');
      return fetch(proxyUrl, { headers: request.headers, method: request.method, body: request.body });
    }

    if (proxyTarget === 'apimart') {
      const proxyUrl = new URL(url.pathname + url.search, 'https://api.apimart.ai');
      proxyUrl.searchParams.delete('proxy');
      return fetch(proxyUrl, { headers: request.headers, method: request.method, body: request.body });
    }

    return new Response('Proxy disabled. Use ?openai_proxy=true&api_key=YOUR_KEY to enable.');

    // const base = url.searchParams.get('base')
    // switch(base) {
    //   case 'api.openai.com' :
    //     url.host = 'api.openai.com';
    //     break;
    //   case 'api.wuyinkeji.com' :
    //     url.host = 'api.wuyinkeji.com';
    //     break;
    //   case 'openrouter.ai' :
    //     url.host = 'openrouter.ai';
    //     break;
    //   default:
    //     return 'no auth';
    // }
    
    // // 创建新的URL对象，指向OpenAI API
    // const proxyUrl = new URL(url.pathname + url.search, 'https://api.openai.com');
    
    // // 移除用于控制代理的查询参数，避免转发给OpenAI
    // proxyUrl.searchParams.delete('api.openai.com');
    // return fetch(url, { headers: request.headers, method: request.method, body: request.body });
  },
};
