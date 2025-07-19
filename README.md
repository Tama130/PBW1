import React, { useState } from "react";
import { Container, Navbar, Button, Form } from "react-bootstrap";
import "bootstrap/dist/css/bootstrap.min.css";
import logo from "./logo192.png"; // Pastikan logo ada di folder src

function App() {
  const [sisi, setSisi] = useState(0);
  const [luasPermukaan, setLuasPermukaan] = useState(0);
  const [volume, setVolume] = useState(0);

  const hitungKubus = () => {
    const s = parseFloat(sisi);
    const luas = 6 * s * s;
    const vol = s * s * s;
    setLuasPermukaan(luas.toFixed(2));
    setVolume(vol.toFixed(2));
  };

  return (
    <div>
      {/* Header */}
      <Navbar
        bg="light"
        className="border"
        style={{
          padding: "10px 20px",
          display: "flex",
          justifyContent: "space-between",
          alignItems: "center",
        }}
      >
        <div
          style={{
            padding: "10px",
            border: "1px solid black",
            borderRadius: "5px",
            minWidth: "250px",
            textAlign: "center",
            fontWeight: "bold",
          }}
        >
          TEMPAT PERHITUNGAN KUBUS TERBAIK
        </div>
        <img
          src={logo}
          alt="Logo"
          style={{
            width: "70px",
            height: "70px",
            borderRadius: "50%",
            objectFit: "cover",
            border: "1px solid black",
          }}
        />
      </Navbar>

      {/* Navigasi */}
      <Container
        className="border py-2"
        style={{
          display: "flex",
          justifyContent: "center",
          gap: "10px",
          marginTop: "10px",
        }}
      >
        <Button variant="outline-dark">HOME</Button>
        <Button variant="outline-dark">PENDAFTARAN</Button>
        <Button variant="outline-dark">INFORMASI</Button>
        <Button variant="outline-dark">KONTAK KAMI</Button>
      </Container>

      {/* Form Hitung */}
      <Container
        className="border p-4 my-4"
        style={{ maxWidth: "500px", textAlign: "left" }}
      >
        <h5 className="mb-3 text-center">Perhitungan Kubus</h5>
        <Form>
          <Form.Group className="mb-3">
            <Form.Label>Panjang Sisi Kubus</Form.Label>
            <Form.Control
              type="number"
              value={sisi}
              onChange={(e) => setSisi(e.target.value)}
            />
          </Form.Group>
          <Button variant="secondary" onClick={hitungKubus} className="mb-3">
            Hitung
          </Button>
          <Form.Group className="mb-3">
            <Form.Label>Luas Permukaan</Form.Label>
            <Form.Control type="text" value={luasPermukaan} readOnly />
          </Form.Group>
          <Form.Group>
            <Form.Label>Volume Kubus</Form.Label>
            <Form.Control type="text" value={volume} readOnly />
          </Form.Group>
        </Form>
      </Container>

      {/* Footer */}
      <footer className="text-center border py-3">
        Tahun Ajaran 2024/2025 <br />
        &copy;copyright 2025
      </footer>
    </div>
  );
}

export default App;
