[index.html.txt](https://github.com/user-attachments/files/24358703/index.html.txt)
function createGojoLikeCharacter() {
  const group = new THREE.Group();

  // ÜST (siyah dar tişört)
  const torso = new THREE.Mesh(
    new THREE.BoxGeometry(1.2, 1.5, 0.6),
    new THREE.MeshStandardMaterial({ color: 0x000000 })
  );
  torso.position.y = 2.2;
  group.add(torso);

  // ALT (bol gri pantolon)
  const pants = new THREE.Mesh(
    new THREE.CylinderGeometry(0.8, 1.0, 1.8, 16),
    new THREE.MeshStandardMaterial({ color: 0xcccccc })
  );
  pants.position.y = 1;
  group.add(pants);

  // KOLLAR
  const armMat = new THREE.MeshStandardMaterial({ color: 0xffe0bd });

  const leftArm = new THREE.Mesh(
    new THREE.CylinderGeometry(0.18, 0.18, 1.4),
    armMat
  );
  leftArm.position.set(-0.9, 2.3, 0);
  leftArm.rotation.z = Math.PI / 10;
  group.add(leftArm);

  const rightArm = leftArm.clone();
  rightArm.position.x = 0.9;
  rightArm.rotation.z = -Math.PI / 10;
  group.add(rightArm);

  // BAŞ
  const head = new THREE.Mesh(
    new THREE.SphereGeometry(0.45, 32, 32),
    new THREE.MeshStandardMaterial({ color: 0xffe0bd })
  );
  head.position.y = 3.3;
  group.add(head);

  // SAÇ (beyaz – Gojo hissi)
  const hair = new THREE.Mesh(
    new THREE.SphereGeometry(0.48, 16, 16),
    new THREE.MeshStandardMaterial({ color: 0xffffff })
  );
  hair.position.y = 3.45;
  group.add(hair);

  return group;
}
