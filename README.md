export default function Prank520Website() {
  const randomMessages = [
    '系统正在验证真心...',
    '检测到恋爱脑浓度过高...',
    'AI正在分析你的嘴硬程度...',
    '爱情服务器已超载...',
    '正在匹配你的舔狗等级...',
  ];

  const escapeButton = (e) => {
    const btn = e.target;
    const maxX = window.innerWidth - 150;
    const maxY = window.innerHeight - 80;

    const x = Math.random() * maxX;
    const y = Math.random() * maxY;

    btn.style.position = 'fixed';
    btn.style.left = `${x}px`;
    btn.style.top = `${y}px`;
    btn.style.transform = `rotate(${Math.random() * 30 - 15}deg)`;
  };

  const fakeLoading = () => {
    const overlay = document.createElement('div');
    overlay.innerHTML = `
      <div id="loadingBox" style="
        position:fixed;
        inset:0;
        background:rgba(0,0,0,0.92);
        display:flex;
        flex-direction:column;
        justify-content:center;
        align-items:center;
        z-index:99999;
        color:white;
        font-family:sans-serif;
      ">
        <h1 style="font-size:42px;margin-bottom:30px;">❤️ 恋爱系统启动中...</h1>
        <div style="width:320px;height:22px;background:#333;border-radius:999px;overflow:hidden;">
          <div id="bar" style="height:100%;width:0%;background:linear-gradient(90deg,#ff4d6d,#ff8fab);"></div>
        </div>
        <p id="text" style="margin-top:20px;color:#aaa;font-size:18px;">${randomMessages[0]}</p>
      </div>
    `;

    document.body.appendChild(overlay);

    const bar = overlay.querySelector('#bar');
    const text = overlay.querySelector('#text');

    let progress = 0;

    const timer = setInterval(() => {
      progress += Math.random() * 15;
      bar.style.width = `${progress}%`;
      text.innerText = randomMessages[Math.floor(Math.random() * randomMessages.length)];

      if (progress >= 100) {
        clearInterval(timer);

        setTimeout(() => {
          overlay.innerHTML = `
            <div style="text-align:center;padding:20px;">
              <h1 style="font-size:70px;">🤡</h1>
              <h2 style="font-size:38px;margin-top:20px;">你居然真信了？</h2>
              <p style="margin-top:15px;color:#999;font-size:20px;">
                本次520表白由“全国深情种协会”特别诈骗播出
              </p>

              <button id="continueBtn" style="
                margin-top:35px;
                padding:14px 40px;
                border:none;
                border-radius:999px;
                background:#ff4d6d;
                color:white;
                font-size:20px;
                cursor:pointer;
              ">
                我不服，再试一次
              </button>
            </div>
          `;

          overlay.querySelector('#continueBtn').onclick = () => {
            overlay.remove();
            trollDesktop();
          };
        }, 1200);
      }
    }, 280);
  };

  const trollDesktop = () => {
    const container = document.createElement('div');
    container.style.position = 'fixed';
    container.style.inset = '0';
    container.style.zIndex = '999999';
    container.style.background = 'linear-gradient(135deg,#111,#000)';
    container.style.overflow = 'hidden';

    document.body.appendChild(container);

    for (let i = 0; i < 25; i++) {
      const popup = document.createElement('div');

      popup.innerHTML = `
        <div style="
          width:260px;
          background:white;
          border-radius:20px;
          box-shadow:0 10px 40px rgba(0,0,0,.4);
          padding:18px;
          font-family:sans-serif;
        ">
          <h3 style="margin:0;color:#ff4d6d;">⚠ 恋爱警告</h3>
          <p style="margin-top:10px;color:#444;line-height:1.5;">
            检测到用户存在严重恋爱幻想，请立即停止深情。
          </p>
          <button style="
            margin-top:12px;
            width:100%;
            border:none;
            background:black;
            color:white;
            padding:10px;
            border-radius:12px;
          ">
            知道了（但下次还敢）
          </button>
        </div>
      `;

      popup.style.position = 'absolute';
      popup.style.left = Math.random() * window.innerWidth + 'px';
      popup.style.top = Math.random() * window.innerHeight + 'px';
      popup.style.animation = `float${i} 2s infinite alternate ease-in-out`;

      container.appendChild(popup);
    }

    const endBtn = document.createElement('button');
    endBtn.innerText = '关闭恶搞';

    endBtn.style.position = 'fixed';
    endBtn.style.bottom = '30px';
    endBtn.style.left = '50%';
    endBtn.style.transform = 'translateX(-50%)';
    endBtn.style.padding = '16px 45px';
    endBtn.style.border = 'none';
    endBtn.style.borderRadius = '999px';
    endBtn.style.background = '#ff4d6d';
    endBtn.style.color = 'white';
    endBtn.style.fontSize = '20px';
    endBtn.style.cursor = 'pointer';

    endBtn.onmouseenter = escapeButton;

    endBtn.onclick = () => {
      container.innerHTML = `
        <div style="
          height:100vh;
          display:flex;
          justify-content:center;
          align-items:center;
          flex-direction:column;
          color:white;
          font-family:sans-serif;
          text-align:center;
        ">
          <h1 style="font-size:90px;">🤣🤣🤣</h1>
          <h2 style="font-size:45px;">520快乐，但你还是单身</h2>
          <p style="margin-top:20px;color:#888;font-size:20px;">
            截图发朋友圈效果更佳
          </p>
        </div>
      `;
    };

    container.appendChild(endBtn);
  };

  return (
    <div className="relative w-full h-screen overflow-hidden bg-gradient-to-br from-pink-500 via-rose-400 to-red-500 flex items-center justify-center text-white">
      <div className="absolute inset-0 bg-[radial-gradient(circle_at_center,white_1px,transparent_1px)] bg-[length:35px_35px] opacity-20" />

      <div className="relative z-10 backdrop-blur-2xl bg-white/10 border border-white/20 rounded-[40px] px-12 py-14 shadow-2xl text-center max-w-2xl">
        <h1 className="text-6xl font-black mb-6 animate-pulse">
          💘 AI智能告白系统
        </h1>

        <p className="text-2xl leading-relaxed opacity-90 mb-3">
          系统通过大数据分析、聊天记录追踪、朋友圈偷窥
        </p>

        <p className="text-3xl font-bold mb-10">
          认定你已经偷偷喜欢很久了 ❤️
        </p>

        <div className="flex justify-center gap-8 flex-wrap">
          <button
            onMouseEnter={escapeButton}
            onClick={escapeButton}
            className="bg-white text-pink-600 font-black px-10 py-5 rounded-full text-2xl shadow-2xl hover:scale-110 transition-all"
          >
            我愿意 😳
          </button>

          <button
            onClick={fakeLoading}
            className="bg-black/30 border border-white/30 text-white font-bold px-10 py-5 rounded-full text-2xl hover:bg-black/50 transition-all"
          >
            考虑一下 🤔
          </button>
        </div>

        <div className="mt-10 text-white/70 text-sm leading-7">
          ⚠ 温馨提示：点击“我愿意”成功率仅 0.0001%<br />
          ⚠ 本系统已接入深情防沉迷机制<br />
          ⚠ 单身用户禁止急眼
        </div>
      </div>

      <div className="absolute bottom-6 text-sm text-white/60">
        © 2026 DeepLove AI · 全国单身联盟技术支持
      </div>
    </div>
  );
}
