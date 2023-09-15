# Frontend
const navbar = [
  { name: 'Home', id: 'home'},
  { name: 'About', id: 'about' },
  { name: 'Our Products', id: 'product', child: [
    { name: 'Product 1', id: 'p1'},
    { name: 'Product 2', id: 'p2' },
    { name: 'Product 3', id: 'p3'},
    { name: 'Product 4', id: 'p4' },
  ] },
  { name: 'Contact Us', id: 'contact'},
];

function createMenu() {
  const menuContainer = document.getElementById('menu');
  
  navbar.forEach(item => {
    const menuItem = document.createElement('li');
    menuItem.textContent = item.name;
    menuItem.setAttribute('id', item.id);
    
    if (item.child) {
      const submenu = document.createElement('ul');
      submenu.classList.add('submenu');
      
      item.child.forEach(subItem => {
        const submenuItem = document.createElement('li');
        submenuItem.textContent = subItem.name;
        submenuItem.setAttribute('id', subItem.id);
        submenu.appendChild(submenuItem);
      });
      
      menuItem.appendChild(submenu);
    }
    
    menuContainer.appendChild(menuItem);
  });
}

createMenu();
