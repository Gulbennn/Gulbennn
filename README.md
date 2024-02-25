import React, { useState, useEffect } from 'react';
import axios from 'axios';

const Nilufer = ({ trafficData }) => {
  const [niluferData, setNiluferData] = useState(null);

  useEffect(() => {
    // Örnek: Nilüfer ilçesine özel trafik verisi alımı
    if (trafficData) {
      const niluferTraffic = trafficData.nilufer; // varsayılan olarak nilufer kullanıldı, gerçek API'ya göre güncellenmeli
      setNiluferData(niluferTraffic);
    }
  }, [trafficData]);

  return (
    <div>
      <h2>Nilüfer İlçesi</h2>
      {niluferData ? (
        <div>
          <p>Trafik Yoğunluğu: {niluferData.trafficLevel}</p>
          <p>Son Güncelleme: {niluferData.lastUpdate}</p>
          {/* Nilüfer, Bursa iline bağlı ilçedir. İlçenin adı, Orhan Gazi'nin eşi "Nilüfer Hatun"dan gelmektedir. */}
        </div>
      ) : (
        <p>Trafik verileri yükleniyor...</p>
      )}
    </div>
  );
};

export default Nilufer;
